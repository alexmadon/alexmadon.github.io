# linux install on lenovo legion 5


# enter bios

boot order:
F12


F2 key repeatedly (or Fn + F2 if F2 alone doesn't work) until the BIOS setup screen appears. 

## nvidia GPU

in BIOS
disable secureBoot


add /etc/apt/sources.list


```
apt install nvidia-detect
```

```
root@msi:~# apt install linux-headers-amd64
```




```
apt install nvidia-driver firmware-misc-nonfree
```


```
madon@msi:~/whisper$ lspci -nnk | grep -E -i --color 'vga|3d|2d' -A3 | grep 'in use'
	Kernel driver in use: nouveau
```

reboot

```
root@msi:~#  lspci -nnk | grep -E -i --color 'vga|3d|2d' -A3 | grep 'in use'
	Kernel driver in use: nvidia
```

## HDMI no signal

in the BIOS: Discrete Graphics mode forces the laptop to use only the dedicated Nvidia GPU

# links

https://gist.github.com/VV0JC13CH/ff9c19325650b5f88c611653b6d3698e


# GIST by VV0JC13CH


# This is a collection of Ubuntu fixes for Lenovo Legion 5i
Tested on:
Lenovo Legion 5i with below specs:\
AMD® Ryzen 7 4800h with radeon graphics × 16 \
NVIDIA Corporation / NVIDIA GeForce RTX 2060/PCIe/SSE2


### 1. GPU ISSUES for RTX 2060:
nvidia-driver-470 - HDMI doesn't have to work from the beginning\
nvidia-driver-495 - HDMI works from the beginning, unstable (random reboots)\
recommended way to install nvidia drivers:\
`sudo ubuntu-drivers autoinstall`

#### 1.1 How to fix external display (HDMI) - no signal
```
sudo prime-select nvidia
reboot
```
#### 1.2 How to fix brightness control
`sudo nano /etc/default/grub`

1.2.1 BIOS in switchable mode:

Add `video.use_native_backlight=1` to `GRUB_CMDLINE_LINUX_DEFAULT` like below:

`GRUB_CMDLINE_LINUX_DEFAULT="quiet splash video.use_native_backlight=1"`

```
sudo update-grub2
reboot
```

1.2.2 BIOS in descrete mode:

Replace content of `GRUB_CMDLINE_LINUX_DEFAULT` with `nvidia-drm.modeset=1 acpi_backlight=native nvidia.NVreg_RegistryDwords=EnableBrightnessControl=1`, like below:

`GRUB_CMDLINE_LINUX="nvidia-drm.modeset=1 acpi_backlight=native nvidia.NVreg_RegistryDwords=EnableBrightnessControl=1"`

```
sudo update-grub2
reboot
```

#### 1.3 Fix backlight error logs during boot
Example: `systemd-backlight[897]: Failed to get backlight or LED device 'backlight:acpi_video1': No such device`
Edit service file:
`sudo nano /lib/systemd/system/systemd-backlight@.service`
Replace content with:
```
[Unit]
Description=Set lower brightness on startup
After=systemd-backlight@backlight:amdgpu_bl0.service

[Service]
Type=oneshot
ExecStart=/bin/bash -c 'echo 25 > /sys/class/backlight/amdgpu_bl0/brightness'
ExecStart=systemctl start --now systemd-backlight@backlight:amdgpu_bl0

[Install]
WantedBy=systemd-backlight@backlight:amdgpu_bl0.service
WantedBy=multi-user.target
```

#### 1.4 Fix amdgpu: Unsupported power profile mode 0
`to-do (I don't know how to fix it currently, but doesn't look critical)`

### 2. BIOS oriented issues:

#### 2.1 Fix "Integrity: problem loading X.509 certificate -65"
```
1. Go to bios during boot by pressing F2
2: Disable the Secure Boot in bios
3: Reset Setup Mode ( this function is in Bios )
4: Launch Ubuntu
5: Enable the Secure Boot in bios
```

Sources:\
https://askubuntu.com/a/1378613 (author: Pierre) \
https://forums.developer.nvidia.com/t/ubuntu-doesnt-detect-my-second-hdmi-display/75076/62?page=4 \
https://www.linux.org/threads/failed-to-start-load-save-screen-backlight-brightness-of-amdgpu_bl1.31998/ \
https://itectec.com/ubuntu/ubuntu-integrity-problem-loading-x-509-certificate-65-before-login/
