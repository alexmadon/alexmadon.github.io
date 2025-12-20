
```
$ pip3 install oci
Collecting oci
  Downloading oci-2.154.1-py3-none-any.whl (30.7 MB)
     |████████████████████████████████| 30.7 MB 18.8 MB/s 
Requirement already satisfied: cryptography<46.0.0,>=3.2.1 in /usr/lib/python3/dist-packages (from oci) (3.3.2)
Collecting circuitbreaker<3.0.0,>=1.3.1
  Downloading circuitbreaker-2.1.3-py3-none-any.whl (7.7 kB)
Collecting python-dateutil<3.0.0,>=2.5.3
  Using cached python_dateutil-2.9.0.post0-py2.py3-none-any.whl (229 kB)
Requirement already satisfied: certifi in /usr/lib/python3/dist-packages (from oci) (2020.6.20)
Collecting pytz>=2016.10
  Downloading pytz-2025.2-py2.py3-none-any.whl (509 kB)
     |████████████████████████████████| 509 kB 72.3 MB/s 
Collecting pyOpenSSL<25.0.0,>=17.5.0
  Downloading pyOpenSSL-24.3.0-py3-none-any.whl (56 kB)
     |████████████████████████████████| 56 kB 794 kB/s 
Collecting cryptography<46.0.0,>=3.2.1
  Downloading cryptography-44.0.3-cp39-abi3-manylinux_2_28_x86_64.whl (4.2 MB)
     |████████████████████████████████| 4.2 MB 79.6 MB/s 
Collecting cffi>=1.12
  Downloading cffi-1.17.1-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (445 kB)
     |████████████████████████████████| 445 kB 77.2 MB/s 
Collecting pycparser
  Downloading pycparser-2.22-py3-none-any.whl (117 kB)
     |████████████████████████████████| 117 kB 89.4 MB/s 
Requirement already satisfied: six>=1.5 in /usr/lib/python3/dist-packages (from python-dateutil<3.0.0,>=2.5.3->oci) (1.16.0)
Installing collected packages: pycparser, cffi, cryptography, pytz, python-dateutil, pyOpenSSL, circuitbreaker, oci
Successfully installed cffi-1.17.1 circuitbreaker-2.1.3 cryptography-44.0.3 oci-2.154.1 pyOpenSSL-24.3.0 pycparser-2.22 python-dateutil-2.9.0.post0 pytz-2025.2
```

```
$ find . -iname oci
./.local/lib/python3.9/site-packages/oci
./.local/lib/python3.9/site-packages/oci/addons/adk/auth/oci
```

# the oci CLI

https://docs.oracle.com/en-us/iaas/Content/API/SDKDocs/cliinstall.htm#InstallingCLI__linux_and_unix

bash -c "$(curl -L https://raw.githubusercontent.com/oracle/oci-cli/master/scripts/install/install.sh)"


ash -c "$(curl -L https://raw.githubusercontent.com/oracle/oci-cli/master/scripts/install/install.sh)"
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 16926  100 16926    0     0   100k      0 --:--:-- --:--:-- --:--:--  100k

    ******************************************************************************
    You have started the OCI CLI Installer in interactive mode. If you do not wish
    to run this in interactive mode, please include the --accept-all-defaults option.
    If you have the script locally and would like to know more about
    input options for this script, then you can run:
    ./install.sh -h
    If you would like to know more about input options for this script, refer to:
    https://github.com/oracle/oci-cli/blob/master/scripts/install/README.rst
    ******************************************************************************
Downloading Oracle Cloud Infrastructure CLI install script from https://raw.githubusercontent.com/oracle/oci-cli/v3.2.1/scripts/install/install.py to /home/ewaseeds69/.tmp/oci_cli_install_tmp_jYoD.
############################################################################################################################################## 100.0%
Running install script.
python3 /home/ewaseeds69/.tmp/oci_cli_install_tmp_jYoD 
-- Verifying Python version.
-- Python version 3.9.2 okay.

===> In what directory would you like to place the install? (leave blank to use '/home/ewaseeds69/lib/oracle-cli'): 
-- Creating directory '/home24/ewaseeds69/lib/oracle-cli'.
-- We will install at '/home24/ewaseeds69/lib/oracle-cli'.

===> In what directory would you like to place the 'oci' executable? (leave blank to use '/home/ewaseeds69/bin'): 
-- The executable will be in '/home24/ewaseeds69/bin'.

===> In what directory would you like to place the OCI scripts? (leave blank to use '/home/ewaseeds69/bin/oci-cli-scripts'): 
-- Creating directory '/home24/ewaseeds69/bin/oci-cli-scripts'.
-- The scripts will be in '/home24/ewaseeds69/bin/oci-cli-scripts'.



-- Run the CLI with /home24/ewaseeds69/bin/oci --help
