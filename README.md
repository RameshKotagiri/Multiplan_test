Warning: Unexpected input(s) 'oci-cli-user', 'oci-cli-tenancy', 'oci-cli-fingerprint', 'oci-cli-key-content', 'oci-cli-region', valid inputs are ['command', 'query', 'silent']
Run oracle-actions/run-oci-cli-command@v1.3.2
Installing Oracle Cloud Infrastructure CLI
Executing Oracle Cloud Infrastructure CLI command

/home/runner/_work/_actions/oracle-actions/run-oci-cli-command/v1.3.2/node_modules/@actions/exec/lib/toolrunner.js:592
                error = new Error(`The process '${this.toolPath}' failed with exit code ${this.processExitCode}`);
^
Error: The process '/home/runner/.local/bin/oci' failed with exit code 2
    at ExecState._setResult (/home/runner/_work/_actions/oracle-actions/run-oci-cli-command/v1.3.2/node_modules/@actions/exec/lib/toolrunner.js:592:1)
    at ExecState.CheckComplete (/home/runner/_work/_actions/oracle-actions/run-oci-cli-command/v1.3.2/node_modules/@actions/exec/lib/toolrunner.js:575:1)
    at ChildProcess.<anonymous> (/home/runner/_work/_actions/oracle-actions/run-oci-cli-command/v1.3.2/node_modules/@actions/exec/lib/toolrunner.js:469:1)
    at ChildProcess.emit (node:events:524:28)
    at maybeClose (node:internal/child_process:1104:16)
    at Process.ChildProcess._handle.onexit (node:internal/child_process:304:5)
