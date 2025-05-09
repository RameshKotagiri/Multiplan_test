#!/bin/bash

# Define the Vault name and other parameters
vault_name="ccp-poc-vlt-001"
compartment_id="ocid1.compartment.oc1..aaaaaaaa6epgbx4ujj5fyqokmrstwwm3gizipwfxkkqpc3zpozwgzmf6ddaq"  # Replace with your actual compartment ID

# List vaults to get the vault ID based on the Vault name
vaults_json=$(oci kms management vault list --compartment-id $compartment_id --config-file /mnt/c/Temp/config)

# Print the JSON output for debugging
echo "Vaults JSON: $vaults_json"

# Parse the vaults and get the vault ID if the vault name matches
vault_id=$(echo "$vaults_json" | jq -r --arg vault_name "$vault_name" '.data[] | select(.["display-name"] == $vault_name) | .id')

# Check if vault ID was found
if [ -z "$vault_id" ]; then
    echo "Vault with display name '$vault_name' not found."
    exit 1
else
    echo "Vault ID: $vault_id"
fi

# Function to fetch secret OCIDs based on the secret names
get_secrets() {
    secrets_json=$(oci vault secret list --compartment-id $compartment_id --config-file /mnt/c/Temp/config)

    # Print the raw JSON output for debugging
    echo "Secrets JSON: $secrets_json"

    # Check if the JSON output is empty or contains errors
    if [ -z "$secrets_json" ]; then
        echo "Error: No secrets found or failed to fetch secrets."
        exit 1
    fi

    # Validate the JSON structure
    echo "$secrets_json" | jq . > /dev/null 2>&1
    if [ $? -ne 0 ]; then
        echo "Error: Invalid JSON structure."
        exit 1
    fi

    # Parse the JSON to extract secret names and IDs
    echo "$secrets_json" | jq -r '.data[] | "\(.["secret-name"]):\(.id)"'
}

# Fetch all secrets from the vault
secrets_list=$(get_secrets)

# Output the secret names and IDs
echo "Secrets List: $secrets_list"

# Validate secret IDs
echo "$secrets_list" | awk -F':' '/ocid1.vaultsecret.oc1../ {print "Valid Secret ID: " $2}'

# Store secret OCIDs in a variable dynamically
# declare -A secrets_id
# while IFS= read -r line; do
#     secret_name=$(echo $line | awk -F':' '{print $1}')
#     secret_id=$(echo $line | awk -F':' '{print $2}')
#     secrets_id[$secret_name]=$secret_id
# done <<< "$secrets_list"

# # Debugging: Print the secrets_id array
# echo "Secrets ID Array: ${!secrets_id[@]}"
#===================================================
# declare -A secrets_id
secret_idl=$(echo "$secrets_list" | awk -F':' '/ocid1.vaultsecret.oc1../ {print "Valid Secret ID: " $2}'|awk -F':' '{print $2}')
while IFS= read -r line; do
    secret_id=$(echo $line | awk -F':' '{print $2}')
    secrets_id[$secret_name]=$secret_id
done <<< "$secret_idl"


# Debugging: Print the secrets_id array
echo "Secrets ID Array: ${!secrets_id[@]}"


# Function to fetch secret value based on the secret name
get_secret_value_by_name() {
    local secret_name=$1
    local secret_ocid=${secrets_id[$secret_name]}
    SECRET_CONTENT=$(oci secrets secret-bundle get --secret-id "$secret_ocid"" --query "data.\"secret-bundle-content\".content" --raw-output --config-file /mnt/c/Temp/config --debug)

    echo "Decoding secret content..."
    DECODED_CONTENT=$(echo "$SECRET_CONTENT" | base64 --decode)

    if [ -z "$DECODED_CONTENT" ]; then
        echo "::error::Secret content is empty after decoding"
        exit 1
    fi

    echo "$DECODED_CONTENT"
}

# Fetch the secret values using OCI CLI with API key authentication
declare -A decoded_secret_values
for secret_name in "${!secrets_id[@]}"; do
    echo "Fetching secret value for secret name: $secret_name"
    secret_value=$(get_secret_value_by_name $secret_name)
    if [ -n "$secret_value" ]; then
        decoded_secret_values[$secret_name]=$secret_value
    else
        echo "Secret value for secret name $secret_name is null or empty. Skipping."
    fi
done

# Debugging: Print the decoded secret values
for secret_name in "${!decoded_secret_values[@]}"; do
    echo "Decoded Secret Value for $secret_name: ${decoded_secret_values[$secret_name]}"
done

# Build the JSON payload dynamically
json_payload=$(jq -n --argjson vars "$(for secret_name in "${!decoded_secret_values[@]}"; do echo "{\"key\": \"$secret_name\", \"value\": \"${decoded_secret_values[$secret_name]}\", \"description\": \"new POC variable\", \"category\": \"terraform\", \"hcl\": false, \"sensitive\": false},"; done | sed '$ s/,$//')" '{data: {type: "vars", attributes: $vars}}')

# Use the secret values in the curl command
curlExe="/usr/bin/curl"

$curlExe \
  --header "Authorization: Bearer pWDB3hxzQdHN2Q.atlasv1.yqJ2D6bI5vQ2oT8zfEqL5YxwYcU9OXnoddazHuAjc6ARzfuOxI7NbsZCdm7EfTxwqUI" \
  --header "Content-Type: application/vnd.api+json" \
  --request POST \
  --data "$json_payload" \
  https://app.terraform.io/api/v2/workspaces/ws-8v5u1xxQFjFWXWSc/vars
 

------------------------------------


###OUTPUT 


DEBUG:oci_cli.cli_metrics: 2025-05-07 13:54:53.920177: Metrics is not enabled

Linux-5.10.102.1-microsoft-standard-WSL2-x86_64-with-glibc2.39

System name: Linux

System release : 5.10.102.1-microsoft-standard-WSL2

System version: #1 SMP Wed Mar 2 00:30:59 UTC 2022
 
env OCI_CLI_SUPPRESS_FILE_PERMISSIONS_WARNING is set

env OCI_PYTHON_SDK_NO_SERVICE_IMPORTS is set

DEBUG:oci_cli.cli_util:Config File: dict_keys(['log_requests', 'additional_user_agent', 'pass_phrase', 'user', 'fingerprint', 'key_file', 'tenancy', 'region'])

DEBUG:oci_cli.cli_util:region: Environment Variable or Parameter

DEBUG:oci.base_client.140466110207840:Endpoint: https://secrets.vaults.us-phoenix-1.oci.oraclecloud.com/20190301

INFO:oci.base_client.140466110207840: 2025-05-07 13:54:54.022876: Request: GET https://secrets.vaults.us-phoenix-1.oci.oraclecloud.com/20190301/secretbundles/%20%7B

Not using Expect header...

send: b'GET /20190301/secretbundles/%20%7B HTTP/1.1\r\nuser-agent: Oracle-PythonSDK/2.150.2 (python 3.12.3; x86_64-Linux) Oracle-PythonCLI/3.54.4\r\naccept-encoding: gzip, deflate\r\naccept: application/json\r\nconnection: keep-alive\r\ncontent-type: application/json\r\nopc-request-id: 889923D94A2B4314AF26C823C52826FC\r\nopc-client-retries: true\r\nopc-client-info: Oracle-PythonSDK/2.150.2\r\ndate: Wed, 07 May 2025 13:54:54 GMT\r\nhost: secrets.vaults.us-phoenix-1.oci.oraclecloud.com\r\nauthorization: Signature algorithm="rsa-sha256",headers="date (request-target) host",keyId="ocid1.tenancy.oc1..aaaaaaaamtvtn7a7y4b7mo7yihimhfbjf5wqhqyzi5t7djdnkoatxyqkq5aa/ocid1.user.oc1..aaaaaaaacawq3yo4d2qoyn6n4dqbqpmump3htnbr6lomafgueki3ffcuxwyq/93:e8:eb:52:32:29:b4:37:87:f6:a1:6b:7e:94:c6:e2",signature="q29z1yn9KeXYWp1SUagZuDauRIvXWtxBujJ9FRNsNOBqZR1dak/DGXwTNStyx9UFxmZ9eMpMV45E4RR39BfunHMFwN6eych62GWcKs9UrUogu2zUQyk+rhnaTRQfu/+8k2ijU7/75eXbpka47yEt349PpFZD8COle5aHsTHiI4/WTm8dTNHIr7U9NrJ/NR3LSq8MES2BX3I+9cXmj5JE7aycPMKiNiRnt2uKxK8IQ47wnc5/Wvjxpo2xlS+fX9ptr0D4RVtz2aGHV5iMVODRhrpI0bPWi2VOHyxNQTFGurn1TwHirrzSEPwosKfc+agWdBDoBUZi5kDcqZ/n4P927g==",version="1"\r\n\r\n'

reply: 'HTTP/1.1 400 Bad Request\r\n'

header: Date: Wed, 07 May 2025 13:54:55 GMT

header: opc-request-id: 889923D94A2B4314AF26C823C52826FC/72D5DB9618D8B856E6FFC1D69511C787/03FAF2F8619B69BF43C2AF48B28804AC

header: Content-Type: application/json

header: X-Content-Type-Options: nosniff

header: Strict-Transport-Security: max-age=31536000; includeSubDomains;

header: Connection: close

header: Content-Length: 82

DEBUG:oci.base_client.140466110207840: 2025-05-07 13:54:54.228901: time elapsed for request 889923D94A2B4314AF26C823C52826FC: 0.205843100000493

DEBUG:oci.base_client.140466110207840: 2025-05-07 13:54:54.229218: Response status: 400

DEBUG:oci.base_client.140466110207840: 2025-05-07 13:54:54.229521: python SDK time elapsed for deserializing: 8.999999408842996e-06

Traceback (most recent call last):
 
