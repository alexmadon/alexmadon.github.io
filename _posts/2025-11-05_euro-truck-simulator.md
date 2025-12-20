# links


https://www.addictivetips.com/ubuntu-linux-tips/how-to-play-euro-truck-simulator-2-on-linux/


wget https://steamcdn-a.akamaihd.net/client/installer/steam.deb


root@toshibalex:/home/madon/usrbin# dpkg -i steam.deb
Selecting previously unselected package steam-launcher.
(Reading database ... 373240 files and directories currently installed.)
Preparing to unpack steam.deb ...
Unpacking steam-launcher (1:1.0.0.85) ...
dpkg: dependency problems prevent configuration of steam-launcher:
 steam-launcher depends on zenity; however:
  Package zenity is not installed.

dpkg: error processing package steam-launcher (--install):
 dependency problems - leaving unconfigured
Processing triggers for mailcap (3.70+nmu1) ...
Processing triggers for desktop-file-utils (0.26-1) ...
Processing triggers for hicolor-icon-theme (0.17-2) ...
Processing triggers for man-db (2.11.2-2) ...
Errors were encountered while processing:
 steam-launcher

adon@toshibalex:~ $ steam
bin_steam.sh[8121]: Setting up Steam content in /home/madon/.local/share/Steam




The packages cache seems to be out of date

Press return to update the list of available packages: 
.......................
These packages are not available:

- steam-libs-amd64:amd64

The Steam client may have limited functionality.
Package libc6:i386 needs to be installed
Package libegl1:i386 needs to be installed
Package libgbm1:i386 needs to be installed
Package libgl1-mesa-dri:i386 needs to be installed
Package libgl1:i386 needs to be installed
Package steam-launcher needs to be installed
Package steam-libs-i386:i386 needs to be installed

Steam needs to install these additional packages:
libc6:amd64 libc6:i386 libegl1:amd64 libegl1:i386 libgbm1:amd64 libgbm1:i386 libgl1-mesa-dri:amd64 libgl1-mesa-dri:i386 libgl1:amd64 libgl1:i386 steam-launcher steam-libs-i386:i386

Press return to proceed with the installation: 

 libc6-dev : Depends: libc6 (= 2.36-9) but 2.36-9+deb12u13 is to be installed
 libegl1:i386 : Depends: libglvnd0:i386 (= 1.6.0-1) but it is not going to be installed
                Depends: libegl-mesa0:i386 but it is not going to be installed
 libgbm1:i386 : Depends: libdrm2:i386 (>= 2.4.75) but it is not going to be installed
                Depends: libexpat1:i386 (>= 2.0.1) but it is not going to be installed
                Depends: libwayland-server0:i386 (>= 1.15.0) but it is not going to be installed
 libgl1:i386 : Depends: libglvnd0:i386 (= 1.6.0-1) but it is not going to be installed
               Depends: libglx0:i386 (= 1.6.0-1) but it is not going to be installed
 libgl1-mesa-dri:i386 : Depends: libdrm-amdgpu1:i386 (>= 2.4.110) but it is not going to be installed
                        Depends: libdrm-intel1:i386 (>= 2.4.38) but it is not going to be installed
                        Depends: libdrm-nouveau2:i386 (>= 2.4.66) but it is not going to be installed
                        Depends: libdrm-radeon1:i386 (>= 2.4.31) but it is not going to be installed
                        Depends: libdrm2:i386 (>= 2.4.75) but it is not going to be installed
                        Depends: libelf1:i386 (>= 0.142) but it is not going to be installed
                        Depends: libexpat1:i386 (>= 2.0.1) but it is not going to be installed
                        Depends: libgcc-s1:i386 (>= 7) but it is not going to be installed
                        Depends: libglapi-mesa:i386 (= 22.3.6-1+deb12u1) but it is not going to be installed
                        Depends: libllvm15:i386 but it is not going to be installed
                        Depends: libsensors5:i386 (>= 1:3.5.0) but it is not going to be installed
                        Depends: libstdc++6:i386 (>= 11) but it is not going to be installed
                        Depends: libxcb-dri3-0:i386 (>= 1.13) but it is not going to be installed
                        Depends: libzstd1:i386 (>= 1.5.2) but it is not going to be installed
                        Depends: zlib1g:i386 (>= 1:1.1.4) but it is not going to be installed
 steam-launcher : Depends: zenity
                  Recommends: steam-libs-amd64
 steam-libs-i386:i386 : Depends: steam-libs:i386 (>= 1:1.0.0.75+ds-6) but it is not going to be installed
E: Unmet dependencies. Try 'apt --fix-broken install' with no packages (or specify a solution).


madon@toshibalex:~ $ steam
bin_steam.sh[8121]: Setting up Steam content in /home/madon/.local/share/Steam
steam.sh[8121]: Running Steam on debian 12 64-bit
steam.sh[8121]: STEAM_RUNTIME is enabled automatically
setup.sh[10449]: Updating Steam runtime environment...
setup.sh[10449]: Forced use of runtime version for 32-bit libcurl-gnutls.so.4
 100%   
steam.sh[8121]: Log already open
steam.sh[8121]: Error: You are missing the following 32-bit libraries, and Steam may not run:
libc.so.6
steam.sh[8121]: Steam client's requirements are satisfied
/home/madon/.local/share/Steam/steam.sh: line 922: /home/madon/.local/share/Steam/ubuntu12_32/steam: cannot execute: required file not found



Steam needs to install these additional packages:
libc6:amd64 libc6:i386 libegl1:amd64 libegl1:i386 libgbm1:amd64 libgbm1:i386 libgl1-mesa-dri:amd64 libgl1-mesa-dri:i386 libgl1:amd64 libgl1:i386 steam-launcher steam-libs-i386:i386

Press return to proceed with the installation: 



8%] Downloading update (399669 of 400704 KB)...
[2025-11-05 18:34:12] Set percent complete: 99
[2025-11-05 18:34:12] Downloading update (400704 of 400704 KB)...
[2025-11-05 18:34:12] Set status message: Downloading update (400704 of 400704 KB)...
[ 99%] Downloading update (400704 of 400704 KB)...
[2025-11-05 18:34:12] Set percent complete: 100
[2025-11-05 18:34:13] Download Complete.
[2025-11-05 18:34:13] Saving metrics to disk (/home/madon/.local/share/Steam/package/steam_client_metrics.bin)
[2025-11-05 18:34:13] uninstalled manifest found in /home/madon/.local/share/Steam/package/steam_client_ubuntu12 (1).
[100%] Downloading update (400704 of 400704 KB)...
[2025-11-05 18:34:13] Set percent complete: 100
[2025-11-05 18:34:13] Set status message: Download Complete.
[10


https://askubuntu.com/questions/611026/steam-error-missing-libgl-so-1
https://askubuntu.com/questions/257084/how-do-i-install-steam-on-a-64bit-system
