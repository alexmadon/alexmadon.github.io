# compress video from rx100m7

https://unix.stackexchange.com/questions/28803/how-can-i-reduce-a-videos-size-with-ffmpeg

ffmpeg -i input.mp4 -vcodec libx265 -crf 28 output.mp4

or

libx264

ffmpeg -i input.avi -filter:v scale=1080:-1 -c:a copy output.mkv
