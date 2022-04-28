https://gist.github.com/kurlov/32cbe841ea9d2b299e15297e54ae8971

FFmpeg can figure out subtitle type and mapping on it's own, nothing fancy needed (assuming your input does not have subtitles in it already):

ffmpeg -i input.mkv -i subtitles.srt -c copy output.mkv


To just add subtitles to file without removing any subtitles it is very easy:

ffmpeg -i input.mkv -i input.srt -map 0 -map 1 -c copy output.mkv

