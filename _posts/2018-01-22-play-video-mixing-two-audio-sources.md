---
date: '2018-01-22T03:10:00.001-0700'
tags: linux screencast presentation mplayer mpv
---



see https://askubuntu.com/questions/768158/how-to-mix-and-play-back-multiple-audio-tracks-from-a-video-file



or multiple inputs or outputs use --lavfi-complex. This example is from man mpv:
```
mpv --lavfi-complex='[aid1][aid2]amix[ao]' input.mkv
```


* A label of the form aidN selects audio track N as input (e.g. aid1).
* A label named ao will be connected to the audio output.

Example with volume filter:

```
mpv --lavfi-complex='[aid1]volume=0.5[vol1];[aid2]volume=3dB[vol2];[vol1][vol2]amix[ao]' input.mkv
```


Note, you need a recent version of `mpv`

https://mpv.io/installation/

https://launchpad.net/~mc3man/+archive/ubuntu/mpv-tests

On ubuntu xenial:

```
sudo add-apt-repository ppa:mc3man/mpv-tests
sudo apt-get update
apt-get install mpv
 ```


```
madon@hp:~$ mpv --version
mpv 0.28.0 (C) 2000-2017 mpv/MPlayer/mplayer2 projects
 built on Thu Dec 28 00:34:43 UTC 2017
ffmpeg library versions:
   libavutil       56.7.100
   libavcodec      58.9.100
   libavformat     58.3.100
   libswscale      5.0.101
   libavfilter     7.7.100
   libswresample   3.0.101
ffmpeg version: git-2017-12-26-e6a1dfc

```

which is known to have lavfi-complex

http://sourcedigit.com/22240-install-mpv-media-player-on-ubuntu-17-04/
MPV Player 0.25

lavfi: support hwdec filters for –lavfi-complex
