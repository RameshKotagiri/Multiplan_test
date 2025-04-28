command: >
      oci secrets secret-bundle get --secret-id "${{ secrets.OCI_VAULT_SECRET_OCID }}" --query "data.\"secret-bundle-content\".content" --raw-output
