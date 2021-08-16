problem:

debain 10.3 does noty have python 38.8 or 3.9


but I want to use:

https://docs.python.org/3/whatsnew/3.8.html#assignment-expressions
# https://www.python.org/dev/peps/pep-0572/



```
# madon@hp:~/jekyll/alexmadon.github.io/_posts$ cat /etc/debian_version 
# 10.3
```


so let's use conda:

```
madon@hp:~$ conda create --name py39 python=3.9
Collecting package metadata (current_repodata.json): done
Solving environment: done


==> WARNING: A newer version of conda exists. <==
  current version: 4.8.3
  latest version: 4.9.2

Please update conda by running

    $ conda update -n base -c defaults conda



## Package Plan ##

  environment location: /home/madon/anaconda3/envs/py39

  added / updated specs:
    - python=3.9


The following packages will be downloaded:

    package                    |            build
    ---------------------------|-----------------
    ca-certificates-2020.10.14 |                0         121 KB
    certifi-2020.11.8          |   py39h06a4308_0         148 KB
    openssl-1.1.1h             |       h7b6447c_0         2.5 MB
    pip-20.3                   |   py39h06a4308_0         1.8 MB
    python-3.9.0               |       hdb3f193_2        18.1 MB
    setuptools-50.3.2          |   py39h06a4308_2         724 KB
    tzdata-2020d               |       h14c3975_0         110 KB
    wheel-0.36.0               |     pyhd3eb1b0_0          32 KB
    ------------------------------------------------------------
                                           Total:        23.5 MB

The following NEW packages will be INSTALLED:

  _libgcc_mutex      pkgs/main/linux-64::_libgcc_mutex-0.1-main
  ca-certificates    pkgs/main/linux-64::ca-certificates-2020.10.14-0
  certifi            pkgs/main/linux-64::certifi-2020.11.8-py39h06a4308_0
  ld_impl_linux-64   pkgs/main/linux-64::ld_impl_linux-64-2.33.1-h53a641e_7
  libedit            pkgs/main/linux-64::libedit-3.1.20191231-h14c3975_1
  libffi             pkgs/main/linux-64::libffi-3.3-he6710b0_2
  libgcc-ng          pkgs/main/linux-64::libgcc-ng-9.1.0-hdf63c60_0
  libstdcxx-ng       pkgs/main/linux-64::libstdcxx-ng-9.1.0-hdf63c60_0
  ncurses            pkgs/main/linux-64::ncurses-6.2-he6710b0_1
  openssl            pkgs/main/linux-64::openssl-1.1.1h-h7b6447c_0
  pip                pkgs/main/linux-64::pip-20.3-py39h06a4308_0
  python             pkgs/main/linux-64::python-3.9.0-hdb3f193_2
  readline           pkgs/main/linux-64::readline-8.0-h7b6447c_0
  setuptools         pkgs/main/linux-64::setuptools-50.3.2-py39h06a4308_2
  sqlite             pkgs/main/linux-64::sqlite-3.33.0-h62c20be_0
  tk                 pkgs/main/linux-64::tk-8.6.10-hbc83047_0
  tzdata             pkgs/main/noarch::tzdata-2020d-h14c3975_0
  wheel              pkgs/main/noarch::wheel-0.36.0-pyhd3eb1b0_0
  xz                 pkgs/main/linux-64::xz-5.2.5-h7b6447c_0
  zlib               pkgs/main/linux-64::zlib-1.2.11-h7b6447c_3


Proceed ([y]/n)? 


Downloading and Extracting Packages
setuptools-50.3.2    | 724 KB    | ######################################################################################################################################################################## | 100% 
openssl-1.1.1h       | 2.5 MB    | ######################################################################################################################################################################## | 100% 
tzdata-2020d         | 110 KB    | ######################################################################################################################################################################## | 100% 
pip-20.3             | 1.8 MB    | ######################################################################################################################################################################## | 100% 
certifi-2020.11.8    | 148 KB    | ######################################################################################################################################################################## | 100% 
ca-certificates-2020 | 121 KB    | ######################################################################################################################################################################## | 100% 
python-3.9.0         | 18.1 MB   | ######################################################################################################################################################################## | 100% 
wheel-0.36.0         | 32 KB     | ######################################################################################################################################################################## | 100% 
Preparing transaction: done
Verifying transaction: done
Executing transaction: done
#
# To activate this environment, use
#
#     $ conda activate py39
#
# To deactivate an active environment, use
#
#     $ conda deactivate
```
