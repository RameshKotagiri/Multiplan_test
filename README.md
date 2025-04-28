- name: Install Dependencies
        run: |
          sudo apt-get update
          sudo apt-get install -y curl jq dnsutils python3 python3-pip python-is-python3
          echo "/home/runner/.local/bin" >> $GITHUB_PATH

      - name: Retrieve Vault Secret using OCI Action
        id: retrieve-secret
        uses: oracle-actions/run-oci-cli-command@v1.3.2
        env:
          OCI_CLI_SUPPRESS_FILE_PERMISSIONS_WARNING: "True"
        with:
          oci-cli-user: ${{ secrets.OCI_USER_OCID }}
          oci-cli-tenancy: ${{ secrets.OCI_TENANCY_OCID }}
          oci-cli-fingerprint: ${{ secrets.OCI_API_FINGERPRINT }}
          oci-cli-key-content: ${{ secrets.OCI_PRIVATE_KEY }}
          oci-cli-region: ${{ secrets.OCI_REGION }}
          command: >
            oci secrets secret-bundle get --secret-id "${{ secrets.OCI_VAULT_SECRET_OCID }}" --query "data.\"secret-bundle-content\".content" --raw-output
            silent: false

      - name: Decode and Parse Vault Secret
        env:
          SECRET_CONTENT: ${{ steps.retrieve-secret.outputs.command-output }}
        run: |
          echo "Decoding secret content..."
          DECODED_CONTENT=$(echo "$SECRET_CONTENT" | base64 --decode)

          if [ -z "$DECODED_CONTENT" ]; then
            echo "::error::Secret content is empty after decoding"
            exit 1
          fi
