$rawSecret = oci secrets secret-bundle get --secret-id "<your-secret-ocid>" --query "data.\"secret-bundle-content\".content" --raw-output
[System.Text.Encoding]::UTF8.GetString([Convert]::FromBase64String($rawSecret))
