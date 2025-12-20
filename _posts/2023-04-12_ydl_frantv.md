# francetv issue

just video!

https://github.com/yt-dlp/yt-dlp/issues/2528

madon@toshibalex:~ $ ydl https://www.france.tv/films/4521088-ice-merchants.html -F
[FranceTVSite] Extracting URL: https://www.france.tv/films/4521088-ice-merchants.html
[FranceTVSite] 4521088-ice-merchants: Downloading webpage
[FranceTV] Extracting URL: francetv:9b91b103-5e79-43d5-b189-560e8a44c04d
[FranceTV] 9b91b103-5e79-43d5-b189-560e8a44c04d: Downloading desktop video JSON
[FranceTV] 9b91b103-5e79-43d5-b189-560e8a44c04d: Downloading mobile video JSON
[FranceTV] 9b91b103-5e79-43d5-b189-560e8a44c04d: Downloading signed dash manifest URL
[FranceTV] 9b91b103-5e79-43d5-b189-560e8a44c04d: Downloading MPD manifest
[FranceTV] 9b91b103-5e79-43d5-b189-560e8a44c04d: Downloading signed hls manifest URL
[FranceTV] 9b91b103-5e79-43d5-b189-560e8a44c04d: Downloading m3u8 information
[info] Available formats for 9b91b103-5e79-43d5-b189-560e8a44c04d:
ID                               EXT RESOLUTION FPS │   FILESIZE   TBR PROTO │ VCODEC        VBR ACODEC     ABR ASR MORE INFO
─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
hls-audio-aacl-96-Audio_Français mp4 audio only     │                  m3u8  │ audio only        unknown            [fr] Audio Français
dash-audio_fre=96000             m4a audio only     │ ~  9.77MiB   96k dash  │ audio only        mp4a.40.2  96k 48k [fr] DASH audio, m4a_dash
dash-video=400000                mp4 384x216     25 │ ~ 40.72MiB  400k dash  │ avc1.42C01E  400k video only         DASH video, mp4_dash
hls-521                          mp4 384x216     25 │ ~ 53.04MiB  521k m3u8  │ avc1.42C01E  521k video only
dash-video=950000                mp4 640x360     25 │ ~ 96.72MiB  950k dash  │ avc1.4D401F  950k video only         DASH video, mp4_dash
hls-1104                         mp4 640x360     25 │ ~112.39MiB 1104k m3u8  │ avc1.4D401F 1104k video only
dash-video=1400000               mp4 960x540     25 │ ~142.53MiB 1400k dash  │ avc1.4D401F 1400k video only         DASH video, mp4_dash
hls-1581                         mp4 960x540     25 │ ~160.96MiB 1581k m3u8  │ avc1.4D401F 1581k video only
dash-video=2000000               mp4 1280x720    25 │ ~203.61MiB 2000k dash  │ avc1.64001F 2000k video only         DASH video, mp4_dash
hls-2217                         mp4 1280x720    25 │ ~225.71MiB 2217k m3u8  │ avc1.64001F 2217k video only
madon@toshibalex:~ $ ydl https://www.france.tv/films/4521088-ice-merchants.html -f dash-audio_fre=96000
[FranceTVSite] Extracting URL: https://www.france.tv/films/4521088-ice-merchants.html
[FranceTVSite] 4521088-ice-merchants: Downloading webpage
[FranceTV] Extracting URL: francetv:9b91b103-5e79-43d5-b189-560e8a44c04d
[FranceTV] 9b91b103-5e79-43d5-b189-560e8a44c04d: Downloading desktop video JSON
[FranceTV] 9b91b103-5e79-43d5-b189-560e8a44c04d: Downloading mobile video JSON
[FranceTV] 9b91b103-5e79-43d5-b189-560e8a44c04d: Downloading signed dash manifest URL
[FranceTV] 9b91b103-5e79-43d5-b189-560e8a44c04d: Downloading MPD manifest
[FranceTV] 9b91b103-5e79-43d5-b189-560e8a44c04d: Downloading signed hls manifest URL
[FranceTV] 9b91b103-5e79-43d5-b189-560e8a44c04d: Downloading m3u8 information
[info] 9b91b103-5e79-43d5-b189-560e8a44c04d: Downloading 1 format(s): dash-audio_fre=96000
[info] There's no subtitles for the requested languages
[SubtitlesConvertor] There aren't any subtitles to convert
[dashsegments] Total fragments: 419
[download] Destination: Ice Merchants [9b91b103-5e79-43d5-b189-560e8a44c04d].m4a
[download] 100% of    9.79MiB in 00:01:33 at 107.75KiB/s
[FixupM4a] Correcting container of "Ice Merchants [9b91b103-5e79-43d5-b189-560e8a44c04d].m4a"
madon@toshibalex:~ $ ls *Merch*
'Ice Merchants [9b91b103-5e79-43d5-b189-560e8a44c04d].m4a'
'Ice Merchants [9b91b103-5e79-43d5-b189-560e8a44c04d].mp4'


madon@toshibalex:~/nathalie/ice_merchants $ ls
ice_merchants__9b91b103_5e79_43d5_b189_560e8a44c04d_.m4a
ice_merchants__9b91b103_5e79_43d5_b189_560e8a44c04d_.mp4

ffmpeg -i ice_merchants__9b91b103_5e79_43d5_b189_560e8a44c04d_.mp4 -i ice_merchants__9b91b103_5e79_43d5_b189_560e8a44c04d_.m4a -c:v copy -c:a copy ice.mp4
