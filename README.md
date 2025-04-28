Run oracle-actions/run-oci-cli-command@v1.3.2
Installing Oracle Cloud Infrastructure CLI
  /usr/bin/python -m pip install oci-cli
  Defaulting to user installation because normal site-packages is not writeable
  Collecting oci-cli
    Downloading oci_cli-3.54.4-py3-none-any.whl (54.4 MB)
       ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 54.4/54.4 MB 8.9 MB/s eta 0:00:00
  Collecting PyYAML<=6.0.1,>=5.4
    Downloading PyYAML-6.0.1-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (705 kB)
       ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 705.5/705.5 KB 17.8 MB/s eta 0:00:00
  Collecting jmespath==0.10.0
    Downloading jmespath-0.10.0-py2.py3-none-any.whl (24 kB)
  Collecting certifi>=2025.1.31
    Downloading certifi-2025.4.26-py3-none-any.whl (159 kB)
       ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 159.6/159.6 KB 9.4 MB/s eta 0:00:00
  Collecting pytz>=2016.10
    Downloading pytz-2025.2-py2.py3-none-any.whl (509 kB)
       ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 509.2/509.2 KB 10.1 MB/s eta 0:00:00
  Requirement already satisfied: six>=1.15.0 in /usr/lib/python3/dist-packages (from oci-cli) (1.16.0)
  Collecting click==8.0.4
    Downloading click-8.0.4-py3-none-any.whl (97 kB)
       ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 97.5/97.5 KB 3.8 MB/s eta 0:00:00
  Collecting python-dateutil<3.0.0,>=2.5.3
    Downloading python_dateutil-2.9.0.post0-py2.py3-none-any.whl (229 kB)
       ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 229.9/229.9 KB 16.4 MB/s eta 0:00:00
  Collecting terminaltables==3.1.10
    Downloading terminaltables-3.1.10-py2.py3-none-any.whl (15 kB)
  Collecting arrow>=1.0.0
    Downloading arrow-1.3.0-py3-none-any.whl (66 kB)
       ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 66.4/66.4 KB 4.3 MB/s eta 0:00:00
  Collecting oci==2.150.2
    Downloading oci-2.150.2-py3-none-any.whl (29.8 MB)
       ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 29.8/29.8 MB 10.2 MB/s eta 0:00:00
  Requirement already satisfied: cryptography<46.0.0,>=3.2.1 in /usr/lib/python3/dist-packages (from oci-cli) (3.4.8)
  Collecting pyOpenSSL<25.0.0,>=17.5.0
    Downloading pyOpenSSL-24.3.0-py3-none-any.whl (56 kB)
       ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 56.1/56.1 KB 2.2 MB/s eta 0:00:00
  Collecting prompt-toolkit<=3.0.43,>=3.0.38
    Downloading prompt_toolkit-3.0.43-py3-none-any.whl (386 kB)
       ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 386.1/386.1 KB 8.3 MB/s eta 0:00:00
  Collecting circuitbreaker<3.0.0,>=1.3.1
    Downloading circuitbreaker-2.1.3-py3-none-any.whl (7.7 kB)
  Collecting types-python-dateutil>=2.8.10
    Downloading types_python_dateutil-2.9.0.20241206-py3-none-any.whl (14 kB)
  Collecting wcwidth
    Downloading wcwidth-0.2.13-py2.py3-none-any.whl (34 kB)
  Collecting cryptography<46.0.0,>=3.2.1
    Downloading cryptography-44.0.2-cp39-abi3-manylinux_2_34_x86_64.whl (4.2 MB)
       ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 4.2/4.2 MB 15.2 MB/s eta 0:00:00
  Collecting cffi>=1.12
    Downloading cffi-1.17.1-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (446 kB)
       ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 446.2/446.2 KB 12.2 MB/s eta 0:00:00
  Collecting pycparser
    Downloading pycparser-2.22-py3-none-any.whl (117 kB)
       ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 117.6/117.6 KB 6.0 MB/s eta 0:00:00
  Installing collected packages: wcwidth, pytz, circuitbreaker, types-python-dateutil, terminaltables, PyYAML, python-dateutil, pycparser, prompt-toolkit, jmespath, click, certifi, cffi, arrow, cryptography, pyOpenSSL, oci, oci-cli
  Successfully installed PyYAML-6.0.1 arrow-1.3.0 certifi-2025.4.26 cffi-1.17.1 circuitbreaker-2.1.3 click-8.0.4 cryptography-44.0.2 jmespath-0.10.0 oci-2.150.2 oci-cli-3.54.4 prompt-toolkit-3.0.43 pyOpenSSL-24.3.0 pycparser-2.22 python-dateutil-2.9.0.post0 pytz-2025.2 terminaltables-3.1.10 types-python-dateutil-2.9.0.20241206 wcwidth-0.2.13
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
