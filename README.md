Retrieve vault secret using OCI action

Run oracle-actions/run-oci-cli-command@v1.3.2
Installing Oracle Cloud Infrastructure CLI
  /home/runner/_work/_tool/Python/3.13.3/x64/bin/python -m pip install oci-cli
  Collecting oci-cli
    Downloading oci_cli-3.54.5-py3-none-any.whl.metadata (7.1 kB)
  Collecting oci==2.150.3 (from oci-cli)
    Downloading oci-2.150.3-py3-none-any.whl.metadata (5.3 kB)
  Collecting arrow>=1.0.0 (from oci-cli)
    Downloading arrow-1.3.0-py3-none-any.whl.metadata (7.5 kB)
  Collecting certifi>=2025.1.31 (from oci-cli)
    Downloading certifi-2025.4.26-py3-none-any.whl.metadata (2.5 kB)
  Collecting click==8.0.4 (from oci-cli)
    Downloading click-8.0.4-py3-none-any.whl.metadata (3.2 kB)
  Collecting cryptography<46.0.0,>=3.2.1 (from oci-cli)
    Downloading cryptography-44.0.2-cp39-abi3-manylinux_2_34_x86_64.whl.metadata (5.7 kB)
  Collecting jmespath==0.10.0 (from oci-cli)
    Downloading jmespath-0.10.0-py2.py3-none-any.whl.metadata (8.0 kB)
  Collecting python-dateutil<3.0.0,>=2.5.3 (from oci-cli)
    Downloading python_dateutil-2.9.0.post0-py2.py3-none-any.whl.metadata (8.4 kB)
  Collecting pytz>=2016.10 (from oci-cli)
    Downloading pytz-2025.2-py2.py3-none-any.whl.metadata (22 kB)
  Collecting six>=1.15.0 (from oci-cli)
    Downloading six-1.17.0-py2.py3-none-any.whl.metadata (1.7 kB)
  Collecting terminaltables==3.1.10 (from oci-cli)
    Downloading terminaltables-3.1.10-py2.py3-none-any.whl.metadata (3.5 kB)
  Collecting pyOpenSSL<25.0.0,>=17.5.0 (from oci-cli)
    Downloading pyOpenSSL-24.3.0-py3-none-any.whl.metadata (15 kB)
  Collecting PyYAML<=6.0.1,>=5.4 (from oci-cli)
    Downloading PyYAML-6.0.1.tar.gz (125 kB)
    Installing build dependencies: started
    Installing build dependencies: finished with status 'done'
    Getting requirements to build wheel: started
    Getting requirements to build wheel: finished with status 'done'
    Preparing metadata (pyproject.toml): started
    Preparing metadata (pyproject.toml): finished with status 'done'
  Collecting prompt-toolkit<=3.0.43,>=3.0.38 (from oci-cli)
    Downloading prompt_toolkit-3.0.43-py3-none-any.whl.metadata (6.5 kB)
  Collecting circuitbreaker<3.0.0,>=1.3.1 (from oci==2.150.3->oci-cli)
    Downloading circuitbreaker-2.1.3-py3-none-any.whl.metadata (8.0 kB)
  Collecting cffi>=1.12 (from cryptography<46.0.0,>=3.2.1->oci-cli)
    Downloading cffi-1.17.1-cp313-cp313-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (1.5 kB)
  Collecting wcwidth (from prompt-toolkit<=3.0.43,>=3.0.38->oci-cli)
    Downloading wcwidth-0.2.13-py2.py3-none-any.whl.metadata (14 kB)
  Collecting types-python-dateutil>=2.8.10 (from arrow>=1.0.0->oci-cli)
    Downloading types_python_dateutil-2.9.0.20241206-py3-none-any.whl.metadata (2.1 kB)
  Collecting pycparser (from cffi>=1.12->cryptography<46.0.0,>=3.2.1->oci-cli)
    Downloading pycparser-2.22-py3-none-any.whl.metadata (943 bytes)
  Downloading oci_cli-3.54.5-py3-none-any.whl (54.4 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 54.4/54.4 MB 28.2 MB/s eta 0:00:00
  Downloading click-8.0.4-py3-none-any.whl (97 kB)
  Downloading jmespath-0.10.0-py2.py3-none-any.whl (24 kB)
  Downloading oci-2.150.3-py3-none-any.whl (29.9 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 29.9/29.9 MB 13.6 MB/s eta 0:00:00
  Downloading terminaltables-3.1.10-py2.py3-none-any.whl (15 kB)
  Downloading circuitbreaker-2.1.3-py3-none-any.whl (7.7 kB)
  Downloading cryptography-44.0.2-cp39-abi3-manylinux_2_34_x86_64.whl (4.2 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 4.2/4.2 MB 13.7 MB/s eta 0:00:00
  Downloading prompt_toolkit-3.0.43-py3-none-any.whl (386 kB)
  Downloading pyOpenSSL-24.3.0-py3-none-any.whl (56 kB)
  Downloading python_dateutil-2.9.0.post0-py2.py3-none-any.whl (229 kB)
  Downloading arrow-1.3.0-py3-none-any.whl (66 kB)
  Downloading certifi-2025.4.26-py3-none-any.whl (159 kB)
  Downloading cffi-1.17.1-cp313-cp313-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (479 kB)
  Downloading pytz-2025.2-py2.py3-none-any.whl (509 kB)
  Downloading six-1.17.0-py2.py3-none-any.whl (11 kB)
  Downloading types_python_dateutil-2.9.0.20241206-py3-none-any.whl (14 kB)
  Downloading pycparser-2.22-py3-none-any.whl (117 kB)
  Downloading wcwidth-0.2.13-py2.py3-none-any.whl (34 kB)
  Building wheels for collected packages: PyYAML
    Building wheel for PyYAML (pyproject.toml): started
    Building wheel for PyYAML (pyproject.toml): finished with status 'done'
    Created wheel for PyYAML: filename=pyyaml-6.0.1-cp313-cp313-linux_x86_64.whl size=45459 sha256=cf69f9e86edc8b667c59cfd0bfa83df56b4e0ec0f5ceff13af224ee01f81526e
    Stored in directory: /home/runner/.cache/pip/wheels/9c/9e/34/1e1548811b63a9d001469f21797e8b7d5c216d8eb928e7d6ad
  Successfully built PyYAML
  Installing collected packages: wcwidth, pytz, circuitbreaker, types-python-dateutil, terminaltables, six, PyYAML, pycparser, prompt-toolkit, jmespath, click, certifi, python-dateutil, cffi, cryptography, arrow, pyOpenSSL, oci, oci-cli
  Successfully installed PyYAML-6.0.1 arrow-1.3.0 certifi-2025.4.26 cffi-1.17.1 circuitbreaker-2.1.3 click-8.0.4 cryptography-44.0.2 jmespath-0.10.0 oci-2.150.3 oci-cli-3.54.5 prompt-toolkit-3.0.43 pyOpenSSL-24.3.0 pycparser-2.22 python-dateutil-2.9.0.post0 pytz-2025.2 six-1.17.0 terminaltables-3.1.10 types-python-dateutil-2.9.0.20241206 wcwidth-0.2.13
Executing Oracle Cloud Infrastructure CLI command
