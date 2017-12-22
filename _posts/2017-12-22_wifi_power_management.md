---
date: '2017-12-22T03:10:00.001-0700'
tags: linux 
---


# xubuntu Xenial 16.04 on HP ZBook 15 G4 (1RQ75ET#ABF)
{:.no_toc}

* TOC
{:toc}

## use of pdftoppm



You can use pdftoppm to convert a PDF to a PNG:

```bash
root@hp:~# iwconfig 
wlp2s0    IEEE 802.11  ESSID:"Livebox-A97E"  
          Mode:Managed  Frequency:2.412 GHz  Access Point: 18:62:2C:7B:A9:7E   
          Bit Rate=130 Mb/s   Tx-Power=22 dBm   
          Retry short limit:7   RTS thr:off   Fragment thr:off
          Encryption key:off
          Power Management:on
          Link Quality=48/70  Signal level=-62 dBm  
          Rx invalid nwid:0  Rx invalid crypt:0  Rx invalid frag:0
          Tx excessive retries:0  Invalid misc:18   Missed beacon:0

virbr0-nic  no wireless extensions.

lo        no wireless extensions.

enp0s31f6  no wireless extensions.

docker0   no wireless extensions.

virbr0    no wireless extensions.

root@hp:/etc/pm/power.d# echo "/sbin/iwconfig wlp2s0 power off" > /etc/pm/power.d/wireless
root@hp:/etc/pm/power.d# /sbin/iwconfig wlp2s0 power off
root@hp:/etc/pm/power.d# iwconfig 
wlp2s0    IEEE 802.11  ESSID:"Livebox-A97E"  
          Mode:Managed  Frequency:2.412 GHz  Access Point: 18:62:2C:7B:A9:7E   
          Bit Rate=130 Mb/s   Tx-Power=22 dBm   
          Retry short limit:7   RTS thr:off   Fragment thr:off
          Encryption key:off
          Power Management:off
          Link Quality=47/70  Signal level=-63 dBm  
          Rx invalid nwid:0  Rx invalid crypt:0  Rx invalid frag:0
          Tx excessive retries:0  Invalid misc:18   Missed beacon:0

virbr0-nic  no wireless extensions.

lo        no wireless extensions.

enp0s31f6  no wireless extensions.

docker0   no wireless extensions.

virbr0    no wireless extensions.

```


https://itechscotland.wordpress.com/2011/09/25/how-to-permanently-turn-off-wi-fi-power-management-in-ubuntu/