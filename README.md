Run echo "Installing OCI CLI..."
Installing OCI CLI...
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed

WARNING: Some interactive prompts may not function correctly if this script is piped into bash (e.g. 'curl "https://raw.githubusercontent.com/oracle/oci-cli/master/scripts/install/install.sh" | bash)'
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
WARNING: Script should either be downloaded and invoked directly, or be run with the following command: bash -c "$(curl -L https://raw.githubusercontent.com/oracle/oci-cli/master/scripts/install/install.sh)"
Running with --accept-all-defaults
Downloading Oracle Cloud Infrastructure CLI install script from https://raw.githubusercontent.com/oracle/oci-cli/v3.2.1/scripts/install/install.py to /tmp/oci_cli_install_tmp_ryqD.
100 16926  100 16926    0     0  59497      0 --:--:-- --:--:-- --:--:-- 59598
#=#=#                                                                         

###########                                                               15.8%
######################################################################## 100.0%
Running install script.
python3 /tmp/oci_cli_install_tmp_ryqD  --accept-all-defaults
Get:1 http://archive.ubuntu.com/ubuntu jammy InRelease [270 kB]
Get:2 http://archive.ubuntu.com/ubuntu jammy-updates InRelease [128 kB]
Get:3 http://archive.ubuntu.com/ubuntu jammy-backports InRelease [127 kB]
Get:4 http://security.ubuntu.com/ubuntu jammy-security InRelease [129 kB]
Get:5 http://archive.ubuntu.com/ubuntu jammy/restricted amd64 Packages [164 kB]
Get:6 http://archive.ubuntu.com/ubuntu jammy/universe amd64 Packages [17.5 MB]
Get:7 http://archive.ubuntu.com/ubuntu jammy/multiverse amd64 Packages [266 kB]
Get:8 http://archive.ubuntu.com/ubuntu jammy/main amd64 Packages [1792 kB]
Get:9 http://security.ubuntu.com/ubuntu jammy-security/main amd64 Packages [2788 kB]
Get:10 http://archive.ubuntu.com/ubuntu jammy-updates/restricted amd64 Packages [4246 kB]
Get:11 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 Packages [3140 kB]
Get:12 http://archive.ubuntu.com/ubuntu jammy-updates/multiverse amd64 Packages [55.7 kB]
Get:13 http://archive.ubuntu.com/ubuntu jammy-updates/universe amd64 Packages [1542 kB]
Get:14 http://security.ubuntu.com/ubuntu jammy-security/restricted amd64 Packages [4000 kB]
Get:15 http://archive.ubuntu.com/ubuntu jammy-backports/universe amd64 Packages [35.2 kB]
Get:16 http://archive.ubuntu.com/ubuntu jammy-backports/main amd64 Packages [82.7 kB]
Get:17 http://security.ubuntu.com/ubuntu jammy-security/universe amd64 Packages [1243 kB]
Get:18 http://security.ubuntu.com/ubuntu jammy-security/multiverse amd64 Packages [47.7 kB]
Get:19 https://ppa.launchpadcontent.net/git-core/ppa/ubuntu jammy InRelease [24.6 kB]
Get:20 https://ppa.launchpadcontent.net/git-core/ppa/ubuntu jammy/main amd64 Packages [4109 B]
Fetched 37.6 MB in 5s (6967 kB/s)
Reading package lists...
Reading package lists...
Building dependency tree...
Reading state information...
The following additional packages will be installed:
  python3-distutils python3-lib2to3 python3-pip-whl python3-setuptools-whl
  python3.10-venv
The following NEW packages will be installed:
  python3-distutils python3-lib2to3 python3-pip-whl python3-setuptools-whl
  python3-venv python3.10-venv
0 upgraded, 6 newly installed, 0 to remove and 26 not upgraded.
Need to get 2691 kB of archives.
After this operation, 4063 kB of additional disk space will be used.
Get:1 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 python3-lib2to3 all 3.10.8-1~22.04 [77.6 kB]
Get:2 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 python3-distutils all 3.10.8-1~22.04 [139 kB]
Get:3 http://archive.ubuntu.com/ubuntu jammy-updates/universe amd64 python3-pip-whl all 22.0.2+dfsg-1ubuntu0.5 [1680 kB]
Get:4 http://archive.ubuntu.com/ubuntu jammy-updates/universe amd64 python3-setuptools-whl all 59.6.0-1.2ubuntu0.22.04.2 [788 kB]
Get:5 http://archive.ubuntu.com/ubuntu jammy-updates/universe amd64 python3.10-venv amd64 3.10.12-1~22.04.9 [5722 B]
Get:6 http://archive.ubuntu.com/ubuntu jammy-updates/universe amd64 python3-venv amd64 3.10.6-1~22.04.1 [1042 B]
debconf: delaying package configuration, since apt-utils is not installed
Fetched 2691 kB in 1s (2053 kB/s)
Selecting previously unselected package python3-lib2to3.
(Reading database ... 
(Reading database ... 5%
(Reading database ... 10%
(Reading database ... 15%
(Reading database ... 20%
(Reading database ... 25%
(Reading database ... 30%
(Reading database ... 35%
(Reading database ... 40%
(Reading database ... 45%
(Reading database ... 50%
(Reading database ... 55%
(Reading database ... 60%
(Reading database ... 65%
(Reading database ... 70%
(Reading database ... 75%
(Reading database ... 80%
(Reading database ... 85%
(Reading database ... 90%
(Reading database ... 95%
(Reading database ... 100%
(Reading database ... 14648 files and directories currently installed.)
Preparing to unpack .../0-python3-lib2to3_3.10.8-1~22.04_all.deb ...
Unpacking python3-lib2to3 (3.10.8-1~22.04) ...
Selecting previously unselected package python3-distutils.
Preparing to unpack .../1-python3-distutils_3.10.8-1~22.04_all.deb ...
Unpacking python3-distutils (3.10.8-1~22.04) ...
Selecting previously unselected package python3-pip-whl.
Preparing to unpack .../2-python3-pip-whl_22.0.2+dfsg-1ubuntu0.5_all.deb ...
Unpacking python3-pip-whl (22.0.2+dfsg-1ubuntu0.5) ...
Selecting previously unselected package python3-setuptools-whl.
Preparing to unpack .../3-python3-setuptools-whl_59.6.0-1.2ubuntu0.22.04.2_all.deb ...
Unpacking python3-setuptools-whl (59.6.0-1.2ubuntu0.22.04.2) ...
Selecting previously unselected package python3.10-venv.
Preparing to unpack .../4-python3.10-venv_3.10.12-1~22.04.9_amd64.deb ...
Unpacking python3.10-venv (3.10.12-1~22.04.9) ...
Selecting previously unselected package python3-venv.
Preparing to unpack .../5-python3-venv_3.10.6-1~22.04.1_amd64.deb ...
Unpacking python3-venv (3.10.6-1~22.04.1) ...
Setting up python3-setuptools-whl (59.6.0-1.2ubuntu0.22.04.2) ...
Setting up python3-pip-whl (22.0.2+dfsg-1ubuntu0.5) ...
Setting up python3-lib2to3 (3.10.8-1~22.04) ...
Setting up python3-distutils (3.10.8-1~22.04) ...
Setting up python3.10-venv (3.10.12-1~22.04.9) ...
Setting up python3-venv (3.10.6-1~22.04.1) ...
Requirement already satisfied: pip in /home/runner/lib/oracle-cli/lib/python3.10/site-packages (22.0.2)
Collecting pip
  Downloading pip-25.0.1-py3-none-any.whl (1.8 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.8/1.8 MB 9.2 MB/s eta 0:00:00
Installing collected packages: pip
  Attempting uninstall: pip
    Found existing installation: pip 22.0.2
    Uninstalling pip-22.0.2:
      Successfully uninstalled pip-22.0.2
Successfully installed pip-25.0.1
Collecting wheel
  Downloading wheel-0.45.1-py3-none-any.whl.metadata (2.3 kB)
Downloading wheel-0.45.1-py3-none-any.whl (72 kB)
Installing collected packages: wheel
Successfully installed wheel-0.45.1
Collecting oci_cli
  Downloading oci_cli-3.54.3-py3-none-any.whl.metadata (7.1 kB)
Collecting oci==2.150.1 (from oci_cli)
  Downloading oci-2.150.1-py3-none-any.whl.metadata (5.3 kB)
Collecting arrow>=1.0.0 (from oci_cli)
  Downloading arrow-1.3.0-py3-none-any.whl.metadata (7.5 kB)
Collecting certifi==2025.1.31 (from oci_cli)
  Downloading certifi-2025.1.31-py3-none-any.whl.metadata (2.5 kB)
Collecting click==8.0.4 (from oci_cli)
  Downloading click-8.0.4-py3-none-any.whl.metadata (3.2 kB)
Collecting cryptography<46.0.0,>=3.2.1 (from oci_cli)
  Downloading cryptography-44.0.2-cp39-abi3-manylinux_2_34_x86_64.whl.metadata (5.7 kB)
Collecting jmespath==0.10.0 (from oci_cli)
  Downloading jmespath-0.10.0-py2.py3-none-any.whl.metadata (8.0 kB)
Collecting python-dateutil<3.0.0,>=2.5.3 (from oci_cli)
  Downloading python_dateutil-2.9.0.post0-py2.py3-none-any.whl.metadata (8.4 kB)
Collecting pytz>=2016.10 (from oci_cli)
  Downloading pytz-2025.2-py2.py3-none-any.whl.metadata (22 kB)
Collecting six>=1.15.0 (from oci_cli)
  Downloading six-1.17.0-py2.py3-none-any.whl.metadata (1.7 kB)
Collecting terminaltables==3.1.10 (from oci_cli)
  Downloading terminaltables-3.1.10-py2.py3-none-any.whl.metadata (3.5 kB)
Collecting pyOpenSSL<25.0.0,>=17.5.0 (from oci_cli)
  Downloading pyOpenSSL-24.3.0-py3-none-any.whl.metadata (15 kB)
Collecting PyYAML<=6.0.1,>=5.4 (from oci_cli)
  Downloading PyYAML-6.0.1-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (2.1 kB)
Collecting prompt-toolkit<=3.0.43,>=3.0.38 (from oci_cli)
  Downloading prompt_toolkit-3.0.43-py3-none-any.whl.metadata (6.5 kB)
Collecting circuitbreaker<3.0.0,>=1.3.1 (from oci==2.150.1->oci_cli)
  Downloading circuitbreaker-2.1.3-py3-none-any.whl.metadata (8.0 kB)
Collecting types-python-dateutil>=2.8.10 (from arrow>=1.0.0->oci_cli)
  Downloading types_python_dateutil-2.9.0.20241206-py3-none-any.whl.metadata (2.1 kB)
Collecting cffi>=1.12 (from cryptography<46.0.0,>=3.2.1->oci_cli)
  Downloading cffi-1.17.1-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (1.5 kB)
Collecting wcwidth (from prompt-toolkit<=3.0.43,>=3.0.38->oci_cli)
  Downloading wcwidth-0.2.13-py2.py3-none-any.whl.metadata (14 kB)
Collecting pycparser (from cffi>=1.12->cryptography<46.0.0,>=3.2.1->oci_cli)
  Downloading pycparser-2.22-py3-none-any.whl.metadata (943 bytes)
Downloading oci_cli-3.54.3-py3-none-any.whl (54.4 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 54.4/54.4 MB 93.2 MB/s eta 0:00:00
Downloading certifi-2025.1.31-py3-none-any.whl (166 kB)
Downloading click-8.0.4-py3-none-any.whl (97 kB)
Downloading jmespath-0.10.0-py2.py3-none-any.whl (24 kB)
Downloading oci-2.150.1-py3-none-any.whl (29.8 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 29.8/29.8 MB 103.2 MB/s eta 0:00:00
Downloading terminaltables-3.1.10-py2.py3-none-any.whl (15 kB)
Downloading arrow-1.3.0-py3-none-any.whl (66 kB)
Downloading cryptography-44.0.2-cp39-abi3-manylinux_2_34_x86_64.whl (4.2 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 4.2/4.2 MB 110.6 MB/s eta 0:00:00
Downloading prompt_toolkit-3.0.43-py3-none-any.whl (386 kB)
Downloading pyOpenSSL-24.3.0-py3-none-any.whl (56 kB)
Downloading python_dateutil-2.9.0.post0-py2.py3-none-any.whl (229 kB)
Downloading pytz-2025.2-py2.py3-none-any.whl (509 kB)
Downloading PyYAML-6.0.1-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (705 kB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 705.5/705.5 kB 28.2 MB/s eta 0:00:00
Downloading six-1.17.0-py2.py3-none-any.whl (11 kB)
Downloading cffi-1.17.1-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (446 kB)
Downloading circuitbreaker-2.1.3-py3-none-any.whl (7.7 kB)
Downloading types_python_dateutil-2.9.0.20241206-py3-none-any.whl (14 kB)
Downloading wcwidth-0.2.13-py2.py3-none-any.whl (34 kB)
Downloading pycparser-2.22-py3-none-any.whl (117 kB)
Installing collected packages: wcwidth, pytz, circuitbreaker, types-python-dateutil, terminaltables, six, PyYAML, pycparser, prompt-toolkit, jmespath, click, certifi, python-dateutil, cffi, cryptography, arrow, pyOpenSSL, oci, oci_cli
Successfully installed PyYAML-6.0.1 arrow-1.3.0 certifi-2025.1.31 cffi-1.17.1 circuitbreaker-2.1.3 click-8.0.4 cryptography-44.0.2 jmespath-0.10.0 oci-2.150.1 oci_cli-3.54.3 prompt-toolkit-3.0.43 pyOpenSSL-24.3.0 pycparser-2.22 python-dateutil-2.9.0.post0 pytz-2025.2 six-1.17.0 terminaltables-3.1.10 types-python-dateutil-2.9.0.20241206 wcwidth-0.2.13
<string>:1: DeprecationWarning: The distutils package is deprecated and slated for removal in Python 3.12. Use setuptools or check PEP 632 for potential alternatives
<string>:1: DeprecationWarning: The distutils.sysconfig module is deprecated, use sysconfig instead
-- Verifying Python version.
-- Python version 3.10.12 okay.
-- Creating directory '/home/runner/lib/oracle-cli'.
-- We will install at '/home/runner/lib/oracle-cli'.
-- The executable will be in '/home/runner/bin'.
-- Creating directory '/home/runner/bin/oci-cli-scripts'.
-- The scripts will be in '/home/runner/bin/oci-cli-scripts'.
-- The optional packages installed will be ''.
-- Executing: ['sudo', 'apt-get', 'update']
-- Installing python3-venv.
-- Executing: ['sudo', 'apt-get', 'install', 'python3-venv', '-y']
-- Trying to use python3 venv.
-- Executing: ['/usr/bin/python3', '-m', 'venv', '/home/runner/lib/oracle-cli']
-- Executing: ['/home/runner/lib/oracle-cli/bin/pip', 'install', '--upgrade', 'pip']
-- Executing: ['/home/runner/lib/oracle-cli/bin/pip', 'install', '--cache-dir', '/tmp/tmpqjxp25zy', 'wheel', '--upgrade']
-- Executing: ['/home/runner/lib/oracle-cli/bin/pip', 'install', '--cache-dir', '/tmp/tmpqjxp25zy', 'oci_cli', '--upgrade']
-- Backed up '/home/runner/.bashrc' to '/home/runner/.bashrc.backup'
-- Tab completion set up complete.
-- If tab completion is not activated, verify that '/home/runner/.bashrc' is sourced by your shell.
-- 
-- ** Run `exec -l $SHELL` to restart your shell. **
-- 
-- Installation successful.
-- Run the CLI with /home/runner/bin/oci --help
Error: Process completed with exit code 1.
