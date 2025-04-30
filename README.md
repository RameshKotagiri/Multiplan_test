Upload API key to Identity domain user

Run oracle-actions/run-oci-cli-command@v1.3.2
Executing Oracle Cloud Infrastructure CLI command
/home/runner/_work/_tool/Python/3.13.3/x64/bin/oci identity-domains api-key create --endpoint *** --domain-ocid *** --schemas ["urn:ietf:params:scim:schemas:oracle:idcs:ApiKey"] --user file://user.json --fingerprint a4:73:9b:31:7e:3a:62:50:11:45:47:e0:2e:53:ef:7a --key "$(cat keys/public.pem)"
ServiceError:
{
    "client_version": "Oracle-PythonSDK/2.150.3, Oracle-PythonCLI/3.54.5",
    "code": null,
    "detail": "Invalid public key header or footer.",
    "logging_tips": "Please run the OCI CLI command using --debug flag to find more debug information.",
    "message": "The service returned error code 400",
    "opc-request-id": "A1A9BE79C8394AC3A5E979F45C67FB44/UohRa0rtj50000000",
    "operation_name": "create_api_key",
    "request_endpoint": "POST ***/admin/v1/ApiKeys",
    "schemas": [
        "urn:ietf:params:scim:api:messages:2.0:Error",
        "urn:ietf:params:scim:api:oracle:idcs:extension:messages:Error"
    ],
    "status": 400,
    "target_service": "identity_domains",
    "timestamp": "2025-04-29T13:38:03.368472+00:00",
    "troubleshooting_tips": "See [https://docs.oracle.com/iaas/Content/API/References/apierrors.htm] for more information about resolving this error. If you are unable to resolve this issue, run this CLI command with --debug option and contact Oracle support and provide them the full error message.",
    "urn:ietf:params:scim:api:oracle:idcs:extension:messages:_error": {
        "messageId": "error.identity.user.invalidHeaderFooter"
    }
}

/home/runner/_work/_actions/oracle-actions/run-oci-cli-command/v1.3.2/node_modules/@actions/exec/lib/toolrunner.js:592
                error = new Error(`The process '${this.toolPath}' failed with exit code ${this.processExitCode}`);
^
Error: The process '/home/runner/_work/_tool/Python/3.13.3/x64/bin/oci' failed with exit code 1
    at ExecState._setResult (/home/runner/_work/_actions/oracle-actions/run-oci-cli-command/v1.3.2/node_modules/@actions/exec/lib/toolrunner.js:592:1)
    at ExecState.CheckComplete (/home/runner/_work/_actions/oracle-actions/run-oci-cli-command/v1.3.2/node_modules/@actions/exec/lib/toolrunner.js:575:1)
    at ChildProcess.<anonymous> (/home/runner/_work/_actions/oracle-actions/run-oci-cli-command/v1.3.2/node_modules/@actions/exec/lib/toolrunner.js:469:1)
    at ChildProcess.emit (node:events:524:28)
    at maybeClose (node:internal/child_process:1104:16)
    at Process.ChildProcess._handle.onexit (node:internal/child_process:304:5)
