- uses: actions/setup-python@v5
        with:
          python-version: '3.13'
      
      - name: Get user GID from user OCID
        id: get_gid
        uses: oracle-actions/run-oci-cli-command@v1.3.2
        with:
          command: identity-domains user get --endpoint ${{ env.DOMAIN_ENDPOINT }} --user-id "ocid1.user.oc1..aaaaaaaax6rvbxorg4wq6wodbt6o4gbkh2w4dkr5qutwwccsqjrtntvjntxa"
          query: 'data.id'
          silent: false

      - name: Write user payload to file
        run: |
          echo "{\"value\": \"${{ steps.get_gid.outputs.raw_output }}\"}" | tr -d '\n\r[:space:]' > user.json
          cat user.json

      - name: Upload API Key to Identity Domain User
        uses: oracle-actions/run-oci-cli-command@v1.3.2
        with:
          command: identity-domains api-key create --endpoint ${{ env.DOMAIN_ENDPOINT }} --domain-ocid ${{ env.DOMAIN_OCID }} --schemas '[\"urn:ietf:params:scim:schemas:oracle:idcs:ApiKey\"]' --user file://user.json --fingerprint '"${{ steps.fingerprint.outputs.fingerprint }}" --key "\"${{ steps.public_key.outputs.public_key }}\""
          silent: false
