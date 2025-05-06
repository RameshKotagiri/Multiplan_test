- name: Debug Credential Endpoint
  env:
    JENKINS_URL: ${{ secrets.JENKINS_BASE_URL }}
    JENKINS_USER: ${{ secrets.JENKINS_USER }}
    JENKINS_API_TOKEN: ${{ secrets.JENKINS_API_TOKEN }}
    CRUMB_FIELD: ${{ steps.crumb.outputs.crumb_field }}
    CRUMB_VALUE: ${{ steps.crumb.outputs.crumb_value }}
  run: |
    echo "Testing endpoint 1: $JENKINS_URL/job/OCI-POC/job/OCI-CCP/credentials/store/folder/domain/_/createCredentials"
    curl -s -I --user "$JENKINS_USER:$JENKINS_API_TOKEN" \
      -H "$CRUMB_FIELD: $CRUMB_VALUE" \
      "$JENKINS_URL/job/OCI-POC/job/OCI-CCP/credentials/store/folder/domain/_/createCredentials"
    echo "Testing endpoint 2: $JENKINS_URL/job/OCI-POC/job/OCI-CCP/credentials/domain/_/createCredentials"
    curl -s -I --user "$JENKINS_USER:$JENKINS_API_TOKEN" \
      -H "$CRUMB_FIELD: $CRUMB_VALUE" \
      "$JENKINS_URL/job/OCI-POC/job/OCI-CCP/credentials/domain/_/createCredentials"
    echo "Testing endpoint 3: $JENKINS_URL/job/OCI-POC/job/OCI-CCP/credentials/createCredentials"
    curl -s -I --user "$JENKINS_USER:$JENKINS_API_TOKEN" \
      -H "$CRUMB_FIELD: $CRUMB_VALUE" \
      "$JENKINS_URL/job/OCI-POC/job/OCI-CCP/credentials/createCredentials"
