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
declare -A secrets_id
while IFS=: read -r secret_name secret_id; do
    if [[ "$secret_id" == ocid1.vaultsecret.oc1.* ]]; then
        secrets_id[$secret_name]=$secret_id
    fi
done <<< "$secrets_list"

# Debugging: Print the secrets_id array
echo "Secrets ID Array: ${!secrets_id[@]}"

# Function to fetch secret value based on the secret name
get_secret_value_by_name() {
    local secret_name=$1
    local secret_ocid=${secrets_id[$secret_name]}
    SECRET_CONTENT=$(oci secrets secret-bundle get --secret-id "$secret_ocid" --query "data.\"secret-bundle-content\".content" --raw-output --config-file /mnt/c/Temp/config --debug)

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
