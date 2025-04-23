Run echo "Fetching secret with OCID: $OCI_VAULT_SECRET_OCID"
Fetching secret with OCID: ***
ServiceError:
{
    "client_version": "Oracle-PythonSDK/2.150.2, Oracle-PythonCLI/3.54.4",
    "code": "InvalidParameter",
    "logging_tips": "Please run the OCI CLI command using --debug flag to find more debug information.",
    "message": "secretId has an invalid type.",
    "opc-request-id": "4DDFE1D473FB474581E602954D74EE47/9583D20B78B8868F32346287F8891EE7/D3B5A386349E77531BE3CA02B5B070EB",
    "operation_name": "get_secret_bundle",
    "request_endpoint": "GET https://secrets.vaults.***.oci.oraclecloud.com/20190301/secretbundles/***",
    "status": 400,
    "target_service": "secrets",
    "timestamp": "2025-04-23T12:06:51.473619+00:00",
    "troubleshooting_tips": "See [https://docs.oracle.com/iaas/Content/API/References/apierrors.htm] for more information about resolving this error. If you are unable to resolve this issue, run this CLI command with --debug option and contact Oracle support and provide them the full error message."
}
Error: Process completed with exit code 1.
