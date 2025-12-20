https://gist.github.com/andreasbotsikas/8bad3df5309dd0383f2e2c450b22481c

ffmpeg -i concat:VTS_01_1.VOB\|VTS_01_2.VOB\|VTS_01_3.VOB\|VTS_01_4.VOB \
-map 0:0 -map 0:1 -map 0:2 -map 0:6 -map 0:5 -map 0:4 \
-c:v libx264 -preset fast -crf 18 \
-c:a copy -metadata:s:a:0 language=ger \
-c:a copy -metadata:s:a:1 language=eng \
-c:s copy -metadata:s:s:0 language=eng \
-c:s copy -metadata:s:s:1 language=ger \
-c:s copy -metadata:s:s:2 language=ger \
-f matroska movie.mkv


https://www.videoconverterfactory.com/tips/ffmpeg-dvd-to-mp4.html

ffmpeg -i "concat:VTS_01_1.VOB|VTS_01_2.VOB|VTS_01_3.VOB" -b:v 1500k -r 30 -vcodec h264 -strict -2 -acodec aac -ar 44100 -f mp4 convert.mp4.


```
ffmpeg -i "concat:VIDEO_TS.VOB|VTS_01_1.VOB|VTS_01_2.VOB|VTS_01_3.VOB" -b:v 1500k -r 30 -vcodec h264 -strict -2 -acodec aac -ar 44100 -f mp4 /home/madon/tmp/convert.mp4


```


```
ffmpeg -i "concat:video_ts.vob|vts_01_1.vob|vts_01_2.vob|vts_01_3.vob" -b:v 1500k -r 30 -vcodec h264 -strict -2 -acodec aac -ar 44100 -f mp4 /home/madon/tmp/convert2.mp4
```



https://unix.stackexchange.com/questions/28803/how-can-i-reduce-a-videos-size-with-ffmpeg



Update 2020: This answer was written in 2009. Since 2013 a video format much better than H.264 is widely available, namely H.265 (better in that it compresses more for the same quality, or gives higher quality for the same size). To use it, replace the libx264 codec with libx265, and push the compression lever further by increasing the CRF value — add, say, 4 or 6, since a reasonable range for H.265 may be 24 to 30. Note that lower CRF values correspond to higher bitrates, and hence produce higher quality videos.

ffmpeg -i input.mp4 -vcodec libx265 -crf 28 output.mp4

You can also specify a libx265 preset, which affects file size and quality.

To see this technique applied using the older H.264 format, see this answer, quoted below for convenience:

    Calculate the bitrate you need by dividing your target size (in bits) by the video length (in seconds). For example for a target size of 1 GB (one gigabyte, which is 8 gigabits) and 10 000 seconds of video (2 h 46 min 40 s), use a bitrate of 800 000 bit/s (800 kbit/s):

    ffmpeg -i input.mp4 -b 800k output.mp4

    Additional options that might be worth considering is setting the Constant Rate Factor, which lowers the average bit rate, but retains better quality. Vary the CRF between around 18 and 24 — the lower, the higher the bitrate.

    ffmpeg -i input.mp4 -vcodec libx264 -crf 20 output.mp4

