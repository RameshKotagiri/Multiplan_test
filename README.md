declare -A secrets_id

while IFS=: read -r secret_name secret_id; do
  if [[ "$secret_id" == ocid1.vaultsecret.oc1.* ]]; then
    secrets_id["$secret_name"]="$secret_id"
  fi
done <<< "$secrets_list"


SECRET_CONTENT=$(oci secrets secret-bundle get --secret-id "$secret_ocid" --query "data.\"secret-bundle-content\".content" --raw-output --config-file /mnt/c/Temp/config --debug)
