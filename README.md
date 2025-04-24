Get Jenkins CSRF Crumb

Run CRUMB_JSON=$(curl -s --user "$JENKINS_USER:$JENKINS_API_TOKEN" "$JENKINS_URL/crumbIssuer/api/json")
  CRUMB_JSON=$(curl -s --user "$JENKINS_USER:$JENKINS_API_TOKEN" "$JENKINS_URL/crumbIssuer/api/json")
  HTTP_STATUS=$(curl -s -o /dev/null -w "%{http_code}" --user "$JENKINS_USER:$JENKINS_API_TOKEN" "$JENKINS_URL/crumbIssuer/api/json")
  if [ "$HTTP_STATUS" -ne 200 ]; then
    echo "::error::Failed to fetch Jenkins CSRF crumb. HTTP Status: $HTTP_STATUS"
    exit 1
  fi
  echo "crumb_field=$(echo $CRUMB_JSON | jq -r .crumbRequestField)" >> $GITHUB_OUTPUT
  echo "crumb_value=$(echo $CRUMB_JSON | jq -r .crumb)" >> $GITHUB_OUTPUT
  shell: /usr/bin/bash -e {0}
  env:
    TENANCY_ID: ocid1.tenancy.oc1..aaaaaaaayhlzwx4nxan2uv4lm6dydhwrgzbppwvacq4g2oexdafz2ndhvaza
    USER_ID: ocid1.user.oc1..aaaaaaaafqevhod5hxbcotk2uf63sorxqjc7tqqjikchs3i4kndodhcc7kwa
    FINGERPRINT: dc:ef:36:d0:cf:33:50:1f:40:4d:0c:4b:82:c1:ec:f1
    REGION: ***
    PRIVATE_KEY: -----BEGIN RSA PRIVATE KEY-----
  2xgF6w8xnff+pbHavPneRFK4Y/r2tP0Veow0+NFzV0foAaq1QeqWJOQ8F3Kumwhu
  +LnW6SnCJ9+1dl4J8O3SWsOswOKtGpgnHnnjuBf8Vt6Rc7wRiFvAIQWETKMTfvTn
  dfW5DoU/13Z2T8RbJrqlJP+iaVa8M8hHQFLKeDPJUYskaNWYm2OHBlPykJhLiVEn
  7eC7SjT58LM+eQlZCzp78n8OdWDlzubZhJK+YHLAKa2nxXxXqt0IZm5CT8K0xtHA
  SMC1zrSI4d1VoA7cWgvku2JPz4J5uHUOG3kPvAIhM/Vxudg1gFO6DF/I/ChoubgO
  slOMkOipObFyIZUsJ9U3Lgp7KjxjJXvIP1sqtI5ZgNukUGM8PTmQy3L0J9/ELz52
  0ywTAFK5mgXmCdI9Crdkg0AjSCvOkueBn/GHppVXriF6icQ5E9dBWRqnHHxRL5vH
  yM5eieK4108sr4z4HrHMbzgoOpz3DFBo9MjcED2DSB8jE2PhLDa0IqbSxK+Q1OFY
  iwJvX7oVZWZff+z2NYtpWZMmDpmDVRJZPpekKvL3Joh1sHUZZbX+Hi99sxmnY1CX
  aEf2KBSgRdHohfs2+jEYtSqes9Wvf66cBy5lCfxzyiCTA4rE6BQxS+QPSLEqOVDp
  O1bzvhyLqDlAtrLqjnmafpaSUScwAGdrtPWl/u3V5twJ8RzfSnHJybKHmWU+qu1L
  xMwiU13cqU5LUE+m6hQseQgBkmCFte4+Zn1/lfAPMEFVDTTAQrfVcBGgNM0n88yx
  8ksJdVCHCHyOcGD3RQhmqTuxod4muHJREuEMAtg8oQ3k2pnx2v1XcSI3TdtD71cM
  r2AnZR66DttJ3Bc8k6H21nw/8XUHv4vHpvHqlKTIfo+ZZzpKqsvyJIE4QNFcK8DQ
  Qu/CJxTQ1uXukp6IO7sGzOU5f1KpYYJKKY7o82Fs/1+qdk7lxkdYtzJ9ej5fbUjH
  GV
    JENKINS_URL: ***
    JENKINS_USER: ***
    JENKINS_API_TOKEN: ***
Error: Process completed with exit code 6.
