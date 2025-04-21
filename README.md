Run echo "Creating OCI configuration..."
  
Creating OCI configuration...
OCI Config (masked):
[DEFAULT]
user=[REDACTED]
fingerprint=[REDACTED]
key_file=~/.oci/private_key.pem
tenancy=[REDACTED]
region=***
Private key exists: -rw------- 1 runner runner 1716 Apr 21 14:15 /home/runner/.oci/private_key.pem

Test General OCI Authentication

Run echo "Testing OCI CLI authentication with 'oci os ns get'..."
Testing OCI CLI authentication with 'oci os ns get'...
DEBUG:oci_cli.cli_metrics: 2025-04-21 14:15:35.123631: Metrics is not enabled
Linux-5.15.0-1078-azure-x86_64-with-glibc2.35
System name: Linux
System release : 5.15.0-1078-azure
System version: #87-Ubuntu SMP Wed Dec 18 19:21:34 UTC 2024
DEBUG:oci_cli.cli_util:Config File: dict_keys(['log_requests', 'additional_user_agent', 'pass_phrase', 'user', 'fingerprint', 'key_file', 'tenancy', 'region'])
DEBUG:oci_cli.cli_util:region: Environment Variable or Parameter
DEBUG:oci.base_client.140571272376912:Endpoint: https://objectstorage.***.oraclecloud.com
INFO:oci.base_client.140571272376912: 2025-04-21 14:15:35.648909: Request: GET https://objectstorage.***.oraclecloud.com/n
DEBUG:oci.base_client.140571272376912: 2025-04-21 14:15:36.760120: time elapsed for request 866563A3966D4429A55A5117153054AC: 1.111126304604113
DEBUG:oci.base_client.140571272376912: 2025-04-21 14:15:36.760489: Response status: 401
DEBUG:oci.base_client.140571272376912: 2025-04-21 14:15:36.760640: python SDK time elapsed for deserializing: 1.7700716853141785e-05
env OCI_CLI_SUPPRESS_FILE_PERMISSIONS_WARNING is set
env OCI_PYTHON_SDK_NO_SERVICE_IMPORTS is set
Not using Expect header...
send: b'GET /n HTTP/1.1\r\nuser-agent: Oracle-PythonSDK/2.150.1 (python 3.10.12; x86_64-Linux) Oracle-PythonCLI/3.54.3\r\naccept-encoding: gzip, deflate\r\naccept: application/json\r\nconnection: keep-alive\r\ncontent-type: application/json\r\nopc-client-request-id: 6AE3285ACE2C43FF8AF52AADA1DFA948\r\nopc-client-retries: true\r\nopc-client-info: Oracle-PythonSDK/2.150.1\r\nopc-request-id: 866563A3966D4429A55A5117153054AC\r\ndate: Mon, 21 Apr 2025 14:15:35 GMT\r\nhost: objectstorage.***.oraclecloud.com\r\nauthorization: Signature algorithm="rsa-sha256",headers="date (request-target) host",keyId="***/***/***",signature="f2AdL071BjVFfMJpdjQBdeeGJLm2EYKO+Qp/nB6Dd/KpHlfZQ714QayhMXwFC7qtgTkQ6mSrqzMSm12cCiGJF0m5cpx0TECQyKrWBb+VRyY/YNmcSORuXm2RYFuFI/dbtvnI65hCRNj9aBAV27k6UMBnSswfaeTn9L3oWWij7H09eUKfjVEIOFpzr0jJmI4i/aH1wZBszFYiyAo05aVNaM5wHj8u+41fKA2YKTlSfGGGiJhkQ4FHglVVmbN+L7Uxeem+IZlh9vbMUqmqL62LrSzM3Vk6h5j0+Z75SndZ2lDbqCf1pbJzR6v+qoMJuEx0usxSKgzbtkTOTgTU7gjuvA==",version="1"\r\n\r\n'
Traceback (most recent call last):
reply: 'HTTP/1.1 401 Unauthorized\r\n'
header: WWW-Authenticate: Casper realm="AUTH_casper"
header: Content-Type: application/json
header: Content-Length: 109
header: opc-client-request-id: 6AE3285ACE2C43FF8AF52AADA1DFA948
header: date: Mon, 21 Apr 2025 14:15:36 GMT
header: opc-request-id: phx-1:6Olw1ieJWWcwE37LO6IafoxkO-fuwm16rbR_k9rU7tylaV-cBcGgdK36wnIrDUTJ
header: x-api-id: native
header: x-content-type-options: nosniff
header: strict-transport-security: max-age=31536000; includeSubDomains
header: access-control-allow-origin: *
header: access-control-allow-methods: POST,PUT,GET,HEAD,DELETE,OPTIONS
header: access-control-allow-credentials: true
header: access-control-expose-headers: access-control-allow-credentials,access-control-allow-methods,access-control-allow-origin,content-length,content-type,date,opc-client-info,opc-client-request-id,opc-request-id,strict-transport-security,www-authenticate,x-api-id,x-content-type-options
Not using Expect header...
send: b'HEAD / HTTP/1.1\r\nHost: iaas.***.oraclecloud.com\r\nUser-Agent: python-requests/2.27.1\r\nAccept-Encoding: gzip, deflate\r\nAccept: */*\r\nConnection: keep-alive\r\n\r\n'
reply: 'HTTP/1.1 404 Not Found\r\n'
header: Date: Mon, 21 Apr 2025 14:15:37 GMT
header: opc-request-id: /CE3ECCD69611643F89FF95A3AC50BBF5/50BD3592B5CEAD441078919C506DBFF4
header: Content-Type: application/json
header: Strict-Transport-Security: max-age=31536000; includeSubDomains;
header: Content-Length: 111
  File "/home/runner/bin/oci", line 8, in <module>
    sys.exit(cli())
  File "/home/runner/lib/oracle-cli/lib/python3.10/site-packages/click/core.py", line 1128, in __call__
    return self.main(*args, **kwargs)
  File "/home/runner/lib/oracle-cli/lib/python3.10/site-packages/click/core.py", line 1053, in main
    rv = self.invoke(ctx)
  File "/home/runner/lib/oracle-cli/lib/python3.10/site-packages/click/core.py", line 1659, in invoke
    return _process_result(sub_ctx.command.invoke(sub_ctx))
  File "/home/runner/lib/oracle-cli/lib/python3.10/site-packages/click/core.py", line 1659, in invoke
    return _process_result(sub_ctx.command.invoke(sub_ctx))
  File "/home/runner/lib/oracle-cli/lib/python3.10/site-packages/click/core.py", line 1659, in invoke
    return _process_result(sub_ctx.command.invoke(sub_ctx))
  File "/home/runner/lib/oracle-cli/lib/python3.10/site-packages/click/core.py", line 1395, in invoke
    return ctx.invoke(self.callback, **ctx.params)
  File "/home/runner/lib/oracle-cli/lib/python3.10/site-packages/click/core.py", line 754, in invoke
    return __callback(*args, **kwargs)
  File "/home/runner/lib/oracle-cli/lib/python3.10/site-packages/click/decorators.py", line 26, in new_func
    return f(get_current_context(), *args, **kwargs)
  File "/home/runner/lib/oracle-cli/lib/python3.10/site-packages/oci_cli/json_skeleton_utils.py", line 78, in wrapped_call
    func(ctx, *args, **kwargs)
  File "/home/runner/lib/oracle-cli/lib/python3.10/site-packages/oci_cli/cli_util.py", line 926, in wrapped_call
    func(ctx, *args, **kwargs)
  File "/home/runner/lib/oracle-cli/lib/python3.10/site-packages/services/object_storage/src/oci_cli_object_storage/generated/objectstorage_cli.py", line 1024, in get_namespace
    result = client.get_namespace(
  File "/home/runner/lib/oracle-cli/lib/python3.10/site-packages/oci/object_storage/object_storage_client.py", line 2336, in get_namespace
    return retry_strategy.make_retrying_call(
  File "/home/runner/lib/oracle-cli/lib/python3.10/site-packages/oci/retry/retry.py", line 308, in make_retrying_call
    response = func_ref(*func_args, **func_kwargs)
  File "/home/runner/lib/oracle-cli/lib/python3.10/site-packages/oci/base_client.py", line 529, in call_api
    response = self.request(request, allow_control_chars, operation_name, api_reference_link)
  File "/home/runner/lib/oracle-cli/lib/python3.10/site-packages/circuitbreaker.py", line 146, in wrapper
    return self.call(function, *args, **kwargs)
  File "/home/runner/lib/oracle-cli/lib/python3.10/site-packages/circuitbreaker.py", line 188, in call
    return func(*args, **kwargs)
  File "/home/runner/lib/oracle-cli/lib/python3.10/site-packages/oci/base_client.py", line 721, in request
    self.raise_service_error(request, response, service_code, message, operation_name, api_reference_link, target_service, request_endpoint, client_version, timestamp, deserialized_data)
  File "/home/runner/lib/oracle-cli/lib/python3.10/site-packages/oci/base_client.py", line 886, in raise_service_error
    raise exceptions.ServiceError(
oci.exceptions.ServiceError: {'target_service': 'object_storage', 'status': 401, 'code': 'NotAuthenticated', 'opc-request-id': 'phx-1:6Olw1ieJWWcwE37LO6IafoxkO-fuwm16rbR_k9rU7tylaV-cBcGgdK36wnIrDUTJ', 'message': 'The required information to complete authentication was not provided.', 'operation_name': 'get_namespace', 'timestamp': '2025-04-21T14:15:36.760556+00:00', 'client_version': 'Oracle-PythonSDK/2.150.1', 'request_endpoint': 'GET https://objectstorage.***.oraclecloud.com/n', 'logging_tips': 'To get more info on the failing request, refer to https://docs.oracle.com/en-us/iaas/tools/python/latest/logging.html for ways to log the request/response details.', 'troubleshooting_tips': "See https://docs.oracle.com/iaas/Content/API/References/apierrors.htm#apierrors_401__401_notauthenticated for more information about resolving this error. Also see https://docs.oracle.com/iaas/api/#/en/objectstorage/20160918/Namespace/GetNamespace for details on this operation's requirements. If you are unable to resolve this ob
OCI authentication failed
Error: Process completed with exit code 1. 
