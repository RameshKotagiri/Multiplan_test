oci secrets secret-bundle get --secret-id <your-secret-ocid> --query "data.\"secret-bundle-content\".content" --raw-output | base64 --decode
*
