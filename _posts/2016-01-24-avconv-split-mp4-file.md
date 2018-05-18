---
layout: post
title: avconv split mp4 file, truncate it by time
date: '2016-01-24T12:04:00.001-08:00'
author: Alex Madon
tags: unix 
modified_time: '2016-04-03T09:07:59.527-07:00'
blogger_id: tag:blogger.com,1999:blog-7521237649117347170.post-874272275527673318
blogger_orig_url: http://tuxunix.blogspot.com/2016/01/avconv-split-mp4-file.html
---

```
avconv -i test.mp4 -vcodec copy -acodec copy -ss 00:00:00 -t 00:00:03 test1.mp4 ```
<br />
<br />
<br />
You can use -to instead of -t to specify the timestamp to which you want to cut. So, instead of -i input -ss 30 -t 10 you could also do -i input -ss 30 -to 40 to achieve the same thing.<br />
<br />
<br />
```
ffprobe -loglevel quiet -of compact=p=0:nk=1 -show_entries format=duration -i file.mp3 <br />
130.768980<br />
```
