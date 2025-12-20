
# play two videos files (in sync)
panopto records each video channel in different files, so to play them in sync:


# play two videos at the same time


https://github.com/mpv-player/mpv/issues/3854

So, if anyone is looking for this, here is what I ended up doing:

    2 videos: mpv <video1> --external-file=<video2> --lavfi-complex='[vid1] [vid2] hstack [vo]'
    4 videos: mpv <video1> --external-file=<video2> --external-file=<video3> --external-file=<video4> --lavfi-complex='[vid1] [vid2] hstack [t1] ; [vid3] [vid4] hstack [t2] ; [t1] [t2] vstack [vo]'


https://www.vlchelp.com/how-to-open-two-videos-side-by-side/

Here are the steps to open two videos side by side in VLC Media Player:

    Go to Media > Open Multiple Files [CTRL + SHIFT + O].
    Click on Add to browse and add the first video.
    Check the ☑ Show more options checkbox.
    Click and check the ☑ Play another media synchronously (extra audio file, …) checkbox.
    Click on Browse next to Extra media.
    Press Add to locate and add the second video.
    Hit Select.
    Finally, click on Play.

