- name: Generate API key pair
  id: public_key
  run: |
    openssl genrsa -aes128 -passout pass:$PASSPHRASE -out keys/private.pem 2048
    openssl rsa -pubout -in keys/private.pem -passin pass:$PASSPHRASE -out keys/public.pem

    # Extract and clean the public key (remove headers/footers and flatten)
    PUBLIC_KEY=$(awk '/-----BEGIN PUBLIC KEY-----/,/-----END PUBLIC KEY-----/ { if (!/-----/) print }' keys/public.pem | tr -d '\n')

    # Pass cleaned key as output
    echo "public_key=$PUBLIC_KEY" >> $GITHUB_OUTPUT


- name: Upload API Key to Identity Domain User
  uses: oracle-actions/run-oci-cli-command@v1.3.2
  with:
    command: |
      oci identity-domains api-key create \
        --endpoint "${{ env.DOMAIN_ENDPOINT }}" \
        --domain-ocid "${{ env.DOMAIN_OCID }}" \
        --schemas '["urn:ietf:params:scim:schemas:oracle:idcs:ApiKey"]' \
        --user file://user.json \
        --fingerprint "${{ steps.fingerprint.outputs.fingerprint }}" \
        --key "${{ steps.public_key.outputs.public_key }}"
    silent: false
