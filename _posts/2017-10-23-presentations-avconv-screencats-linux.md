---
date: '2017-10-23T03:10:00.001-0700'
tags: linux screencast presentation
---

# Recording Presentations with linux and avconv

When doing presentations a vnc server mught be useful:

```bash
xrandr -q
tightvncserver -alwaysshared -geometry 800x600 -depth 24
tightvncserver -alwaysshared -geometry 1200x800 -depth 24
tightvncserver -alwaysshared -geometry 1024x768 -depth 24
tightvncserver -alwaysshared -geometry 1440x800  -depth 24 -compatiblekbd


xtightvncviewer localhost:1 

xtightvncviewer 10.245.50.94:1 
xtightvncviewer -display :0.1 10.240.8.235:1 
```



# xrandr -q

recordmydesktop --device hw:1,0 -x 1600 -y 0 --width 1024 --height 768


```bash
screenruler
avconv -f alsa -ac 1 -i hw:1,0 -f x11grab -r 30 -s 600x400 -i :0.0+0,0 -strict experimental out23.mp4
avconv -f alsa -ac 1 -i hw:1,0 -f x11grab -r 30 -s 1600x900  -i :0.0+0,0 -strict experimental out23.mp4
avconv -f alsa -ac 2 -i hw:1,0 -f x11grab -r 30 -s 1920x1080 -i :0.0+0,0 -strict experimental out23.mp4
avconv -f pulse -i 2 -f x11grab -r 30 -s 1920x1080 -i :0.0+0,0 -strict experimental out23.mp4
```


Other things I tried:

```bash
recordmydesktop --device hw:1,0


/usr/bin/vnc2swf -o pres1.flv localhost:1

arecord -f S16_LE -c 1 -D hw:1,0 tt.wav

tightvncserver -kill  :1

check the record button is red in also mixer

flvrec.py -P pwd -S 'arecord -f S16_LE -D hw:1,0 tt.wav' localhost:1
arecord -f S16_LE -D hw:1,0 tt.wav
mplayer out201103231349.flv -audiofile tt.wav 


thserver:
==========
vnc4server -geometry 1024x768 -depth 24 BAAAAAAD

 vnc4server -kill :1  

New 'amadon:1 (madon)' desktop is amadon:1

Starting applications specified in /home/madon/.vnc/xstartup
Log file is /home/madon/.vnc/amadon:1.log
----------------
tightvncserver -alwaysshared -geometry 1024x768 -depth 24
tightvncserver -alwaysshared -geometry 1200x600 -depth 24
tightvncserver -kill  :1

client:
=======
Linux:
--------
xvnc4viewer localhost:1 
xvnc4viewer -display :0.1 localhost:1 
xvnc4viewer 10.240.8.235:1

xtightvncviewer localhost:1 
xtightvncviewer  10.240.8.235:1 
xtightvncviewer -display :0.1 10.240.8.235:1 


tightvncserver -alwaysshared -geometry 1024x768 -depth 24



10.240.8.235:1




Windows:
---------
http://www.tightvnc.com/download.php
tightvnc viewer



~/.config/openbox/autostart.sh


===================

/usr/bin/vnc2swf screen recording tool with Flash (SWF) output
/usr/bin/vnc2swf -h
 /usr/bin/vnc2swf -o pres1.flv localhost:5901

madon@madona:~/presentation$ arecord -l
**** List of CAPTURE Hardware Devices ****
card 0: Intel [HDA Intel], device 0: STAC92xx Analog [STAC92xx Analog]
  Subdevices: 2/2
  Subdevice #0: subdevice #0
  Subdevice #1: subdevice #1
card 1: Headset [Plantronics Headset], device 0: USB Audio [USB Audio]
  Subdevices: 1/1
  Subdevice #0: subdevice #0


# arecord tt
Recording WAVE 'tt' : Unsigned 8 bit, Rate 8000 Hz, Mono
arecord: set_params:1053: Sample format non available
Available formats:
- S16_LE
- S32_LE

arecord -f S32_LE foobar.wav
arecord -f S16_LE -c 2 -D hw:1,0 tt.wav
Recording WAVE 'tt.wav' : Signed 16 bit Little Endian, Rate 8000 Hz, Stereo
Warning: rate is not accurate (requested = 8000Hz, got = 44100Hz)
         please, try the plug plugin (-Dplug:default)
arecord -f S16_LE -D -c 2 tt.wav



madon@madona:~/presentation$ arecord -l
**** List of CAPTURE Hardware Devices ****
card 0: PCH [HDA Intel PCH], device 0: STAC92xx Analog [STAC92xx Analog]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 1: Headset [Logitech USB Headset], device 0: USB Audio [USB Audio]
  Subdevices: 1/1
  Subdevice #0: subdevice #0


how to find out the ID
http://askubuntu.com/questions/410737/record-desktop-and-microphone-audio-with-avconv
madon@madona:~/presentation$ pactl list short sources
0	alsa_output.pci-0000_00_03.0.hdmi-stereo.monitor	module-alsa-card.c	s16le 2ch 44100Hz	RUNNING
3	alsa_output.pci-0000_00_1b.0.analog-stereo.monitor	module-alsa-card.c	s16le 2ch 44100Hz	RUNNING
9	alsa_output.usb-Logitech_Logitech_USB_Headset-00-Headset.analog-stereo.monitor	module-alsa-card.c	s16le 2ch 48000Hz	RUNNING
10	alsa_input.usb-Logitech_Logitech_USB_Headset-00-Headset.analog-mono	module-alsa-card.c	s16le 1ch 48000Hz	RUNNING
```