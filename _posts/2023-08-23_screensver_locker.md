root         919  7.2  0.4 1151900 80848 tty7    Rsl+ Aug20 341:06  \_ /usr/lib/xorg/Xorg :0 -seat seat0 -auth /var/run/lightdm/root/:0 -nolisten tcp vt7 -novtswitch
root        1476  0.0  0.0 162424  5188 ?        Sl   Aug20   0:00  \_ lightdm --session-child 13 24
madon       1856  0.0  0.2 289400 37692 ?        Ssl  Aug20   2:41      \_ xfce4-session
madon       1929  0.0  0.0   7660    44 ?        Ss   Aug20   0:01          \_ /usr/bin/ssh-agent /usr/bin/im-launch x-session-manager
madon       1976  1.3  0.3 936616 49204 ?        Sl   Aug20  63:39          \_ xfwm4 --display :0.0 --sm-client-id 2c33efea6-a1ba-4a72-872e-574b0cdd73dc
madon       1999  0.3  0.2 254832 42560 ?        Sl   Aug20  15:01          \_ xfsettingsd --display :0.0 --sm-client-id 2f616b952-9cde-4ff7-8a8e-591e85982aca
madon       2012  0.2  0.4 609812 70072 ?        Sl   Aug20  11:26          \_ xfce4-panel --display :0.0 --sm-client-id 26c1c29b7-8a4b-431a-990b-dea175132bc3
madon       2025  0.0  0.2 430320 44112 ?        Sl   Aug20   0:44          |   \_ /usr/lib/x86_64-linux-gnu/xfce4/panel/wrapper-2.0 /usr/lib/x86_64-linux-gnu/xfce4/panel/plugins/libnotification-plugin.so 10 14680075 notification-plugin Notification Plugin Notification plugin for the Xfce panel
madon       2058  0.0  0.2 448048 33656 ?        Sl   Aug20   1:36          \_ light-locker



https://wiki.debian.org/light-locker



root@toshibalex:/etc/X11# lspci 
00:00.0 Host bridge: Intel Corporation Xeon E3-1200 v5/E3-1500 v5/6th Gen Core Processor Host Bridge/DRAM Registers (rev 08)
00:02.0 VGA compatible controller: Intel Corporation Skylake GT2 [HD Graphics 520] (rev 07)
00:14.0 USB controller: Intel Corporation Sunrise Point-LP USB 3.0 xHCI Controller (rev 21)
00:14.2 Signal processing controller: Intel Corporation Sunrise Point-LP Thermal subsystem (rev 21)
00:16.0 Communication controller: Intel Corporation Sunrise Point-LP CSME HECI #1 (rev 21)
00:17.0 SATA controller: Intel Corporation Sunrise Point-LP SATA Controller [AHCI mode] (rev 21)
00:1c.0 PCI bridge: Intel Corporation Sunrise Point-LP PCI Express Root Port #2 (rev f1)
00:1c.2 PCI bridge: Intel Corporation Sunrise Point-LP PCI Express Root Port #3 (rev f1)
00:1f.0 ISA bridge: Intel Corporation Sunrise Point-LP LPC Controller (rev 21)
00:1f.2 Memory controller: Intel Corporation Sunrise Point-LP PMC (rev 21)
00:1f.3 Audio device: Intel Corporation Sunrise Point-LP HD Audio (rev 21)
00:1f.4 SMBus: Intel Corporation Sunrise Point-LP SMBus (rev 21)
00:1f.6 Ethernet controller: Intel Corporation Ethernet Connection I219-V (rev 21)
01:00.0 Unassigned class [ff00]: Realtek Semiconductor Co., Ltd. RTS5227 PCI Express Card Reader (rev 01)
02:00.0 Network controller: Intel Corporation Wireless 8260 (rev 3a)


root@toshibalex:/etc/X11# grep -i module /var/log/Xorg.0.log


root@toshibalex:/etc/X11/xorg.conf.d# cat 20-intel.conf
Section "Device"
 Identifier  "Intel Graphics"
 Driver      "Intel"
EndSection



ightdm is not a proper screen locker. I guess you have light-locker installed and running. It might not be possible to make a screensaver use physlock, unless you use a configurable screensaver such as xautolock. And, due to an issue automatic locking with suspend might not use xflock4 for locking;  you might have to terminate and uninstall screensavers and/or light-locker that have a higher priority.

You do not need to change xflock4 to be able to use physlock. You can set up a respective xfconf variable by

xfconf-query -c xfce4-session -p /general/LockCommand -s 'physlock -dm' --create -t string

