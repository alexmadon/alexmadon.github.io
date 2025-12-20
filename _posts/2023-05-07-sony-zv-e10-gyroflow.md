# videos from sony zv-e10 on linux
sony catalyst browse

or

gyroflow

vlc behaves better than mplayer on high FPS

https://github.com/gyroflow/gyroflow
https://github.com/gyroflow/gyroflow/releases

tar -xzvf Gyroflow-linux64.tar.gz 
cd Gyroflow/
madon@toshibalex:~/usrbin/Gyroflow $ ./gyroflow 
./gyroflow: error while loading shared libraries: libc++.so.1: cannot open shared object file: No such file or directory

apt install libva2 libvdpau1 libasound2 libxkbcommon0 libpulse0 libc++-dev libvulkan1

The following NEW packages will be installed:
  libc++-11-dev libc++-dev libc++1-11 libc++abi1-11

# gyroflow CLI syntax

```
madon@toshibalex:~/usrbin/Gyroflow $ ./gyroflow --help
MDK 0.20.0 (git 3dd65ad) - Multimedia Development Kit. Copyright (c) 2016-2023 WangBin(QtAV author) <wbsecg1 at gmail.com>
Build for: Linux x86_64; Clang16.0.0 (++20230306093126+ae37edf1486d-1~exp1~20230306213138.48)GCC4.2.1; libc++160000; 01:35:31 Mar  7 2023
19:18:28 [DEBUG] (1) gyroflow: [in main] Qt version: 6.4.2
19:18:28 [DEBUG] (1) gyroflow: Gyroflow 1.5.0 (gh1128)
Usage: gyroflow [<input...>] [-f] [-j <parallel-renders>] [-d <when-done>] [-p <out-params>] [--export-project <export-project>] [--preset <preset>] [--open <open>] [--watch <watch>] [-g <gyro-file>]

Gyroflow v1.5.0
Video stabilization using gyroscope data

Positional Arguments:
  input             input files: videos, project files, lens profiles, presets

Options:
  -f, --overwrite   overwrite if output file exists, default: false
  -j, --parallel-renders
                    number of parallel renders, default: 1
  -d, --when-done   when done: 1 - shut down; 2 - reboot; 3 - sleep; 4 - hibernate; 5 - logout
  -p, --out-params  output parameters, eg. "{ 'codec': 'H.265/HEVC', 'bitrate': 150, 'use_gpu': true, 'audio': true }"
  --export-project  export project file instead of rendering: 1 - default
                    project, 2 - with gyro data, 3 - with processed gyro data
  --preset          preset (file or content directly), eg. "{ 'version': 2, 'stabilization': { 'fov': 1.5 } }"
  --open            open file in the GUI (video or project)
  --watch           watch folder for automated processing
  -g, --gyro-file   gyro file path
  --help            display usage information
```

# gyroflow CLI example

```
madon@toshibalex:~/gyroflow $ ~/usrbin/Gyroflow/gyroflow C0051.MP4 
MDK 0.20.0 (git 3dd65ad) - Multimedia Development Kit. Copyright (c) 2016-2023 WangBin(QtAV author) <wbsecg1 at gmail.com>
Build for: Linux x86_64; Clang16.0.0 (++20230306093126+ae37edf1486d-1~exp1~20230306213138.48)GCC4.2.1; libc++160000; 01:35:31 Mar  7 2023
19:10:01 [DEBUG] (1) gyroflow: [in main] Qt version: 6.4.2
19:10:01 [DEBUG] (1) gyroflow: Gyroflow 1.5.0 (gh1128)
19:10:01 [INFO] Videos: ["C0051.MP4"]
19:10:01 [INFO] Lens profiles directory: "/home/madon/usrbin/Gyroflow/camera_presets"
19:10:01 [INFO] Loaded 6390 lens profiles in 141.639ms
19:10:11 [ERROR] thread 'main' panicked at 'Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))': /root/.cargo/git/checkouts/ocl-51b7c5264cbf134c/d0f4b61/ocl/src/standard/platform.rs:49
   0: <unknown>
   1: <unknown>
   2: <unknown>
   3: <unknown>
   4: <unknown>
   5: <unknown>
   6: <unknown>
   7: <unknown>
   8: <unknown>
   9: <unknown>
  10: <unknown>
  11: <unknown>
  12: <unknown>
  13: main
  14: __libc_start_main
  15: <unknown>

19:10:11 [ERROR] Failed to initialize OpenCL Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))
MESA-INTEL: warning: Performance support disabled, consider sysctl dev.i915.perf_stream_paranoid=0

[src/cli.rs:413] &settings = {
    "safeAreaGuide": "false",
    "defaultOverwriteAction": "0",
    "marginPixels": "0.2",
    "width": "1366",
    "exportAudio": "true",
    "leftPanelSize": "340",
    "showFeatures": "true",
    "timelineChart": "0",
    "x": "0",
    "r3dConvertFormat": "0",
    "backgroundMode": "0",
    "height": "685",
    "adaptiveZoom": "4",
    "initialOffset": "0",
    "padWithBlack": "false",
    "y": "51",
    "correctionAmount": "1",
    "processingResolution": "3",
    "rightPanelSize": "340",
    "r3dColorMode": "0",
    "renderBackground": "#111111",
    "visibility": "4",
    "videoSpeedAffectsZooming": "true",
    "zoomingMethod": "0",
    "smoothing-1-trim_range_only": "0",
    "showOF": "true",
    "theme": "1",
    "parallelRenders": "1",
    "smoothing-1-smoothness_roll": "0.5",
    "smoothing-1-max_smoothness": "1",
    "defaultSuffix": "_stabilized",
    "smoothingMethod": "1",
    "smoothing-1-smoothness": "0.5",
    "croppingMode": "1",
    "defaultCodec": "1",
    "maxSyncPoints": "3",
    "smoothing-1-smoothness_pitch": "0.5",
    "exeLocation": "/home/madon/usrbin/Gyroflow/gyroflow",
    "smoothing-1-second_pass": "1",
    "previewPipeline": "0",
    "timePerSyncpoint": "1.5",
    "experimentalAutoSyncPoints": "false",
    "smoothing-1-smoothness_yaw": "0.5",
    "syncSearchSize": "5",
    "videoSpeedAffectsSmoothing": "true",
    "keyframeDistance": "1",
    "sync_lpf": "0",
    "previewResolution": "0",
    "lang": "en",
    "useGravityVectors": "false",
    "playSounds": "true",
    "gpudecode": "true",
    "smoothing-1-alpha_0_1s": "0.1",
    "exportMode": "0",
    "checkNegativeInitialOffset": "false",
    "smoothing-1-per_axis": "0",
    "preserveOtherTracks": "false",
    "uiScaling": "2",
    "featherPixels": "0.05",
}
[mov,mp4,m4a,3gp,3g2,mj2 @ 0x7faf68000c40] st: 0 edit list: 1 Missing key frame while searching for timestamp: 1000
19:10:11 [WARN] [mov,mp4,m4a,3gp,3g2,mj2 @ 0x7faf68000c40] st: 0 edit list: 1 Missing key frame while searching for timestamp: 1000
[mov,mp4,m4a,3gp,3g2,mj2 @ 0x7faf68000c40] st: 0 edit list 1 Cannot find an index entry before timestamp: 1000.
19:10:11 [WARN] [mov,mp4,m4a,3gp,3g2,mj2 @ 0x7faf68000c40] st: 0 edit list 1 Cannot find an index entry before timestamp: 1000.
19:10:11 [INFO] Loaded VideoInfo { duration_ms: 18240.000000000004, frame_count: 456, fps: 25.0, width: 3840, height: 2160, bitrate: 95.33500957489014 }
19:10:11 [INFO] CameraIdentifier {
    brand: "Sony",
    model: "ZV-E10",
    lens_model: "",
    lens_info: "825191e",
    focal_length: None,
    camera_setting: "",
    fps: 25000,
    video_width: 3840,
    video_height: 2160,
    additional: "",
    identifier: "sony-zv-e10-825191e-3840x2160@25000",
}
19:10:11 [INFO] [8bd0fce3] Processing done
[mov,mp4,m4a,3gp,3g2,mj2 @ 0x7faf60001100] st: 0 edit list: 1 Missing key frame while searching for timestamp: 1000
19:10:11 [WARN] [mov,mp4,m4a,3gp,3g2,mj2 @ 0x7faf60001100] st: 0 edit list: 1 Missing key frame while searching for timestamp: 1000
[mov,mp4,m4a,3gp,3g2,mj2 @ 0x7faf60001100] st: 0 edit list 1 Cannot find an index entry before timestamp: 1000.
19:10:11 [WARN] [mov,mp4,m4a,3gp,3g2,mj2 @ 0x7faf60001100] st: 0 edit list 1 Cannot find an index entry before timestamp: 1000.
[AVHWDeviceContext @ 0x7faf60002980] cu->cuInit(0) failed19:10:12 [ERROR] [AVHWDeviceContext @ 0x7faf60002980] cu->cuInit(0) failed
 -> CUDA_ERROR_NO_DEVICE: no CUDA-capable device is detected19:10:12 [ERROR] -> CUDA_ERROR_NO_DEVICE: no CUDA-capable device is detected

19:10:12 [ERROR] 
19:10:22 [ERROR] thread '<unnamed>' panicked at 'Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))': /root/.cargo/git/checkouts/ocl-51b7c5264cbf134c/d0f4b61/ocl/src/standard/platform.rs:49
   0: <unknown>
   1: <unknown>
   2: <unknown>
   3: <unknown>
   4: <unknown>
   5: <unknown>
   6: <unknown>
   7: <unknown>
   8: <unknown>
   9: <unknown>
  10: <unknown>
  11: <unknown>
  12: <unknown>
  13: <unknown>
  14: <unknown>
  15: <unknown>
  16: <unknown>
  17: <unknown>
  18: <unknown>
  19: <unknown>
  20: <unknown>
  21: <unknown>
  22: start_thread
  23: clone

19:10:22 [ERROR] Failed to initialize OpenCL Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))
19:10:22 [ERROR] Failed to initialize wgpu RequestDevice(RequestDeviceError)
19:10:33 [ERROR] thread '<unnamed>' panicked at 'Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))': /root/.cargo/git/checkouts/ocl-51b7c5264cbf134c/d0f4b61/ocl/src/standard/platform.rs:49
   0: <unknown>
   1: <unknown>
   2: <unknown>
   3: <unknown>
   4: <unknown>
   5: <unknown>
   6: <unknown>
   7: <unknown>
   8: <unknown>
   9: <unknown>
  10: <unknown>
  11: <unknown>
  12: <unknown>
  13: <unknown>
  14: <unknown>
  15: <unknown>
  16: <unknown>
  17: <unknown>
  18: <unknown>
  19: <unknown>
  20: <unknown>
  21: <unknown>
  22: start_thread
  23: clone

19:10:33 [ERROR] Failed to initialize OpenCL Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))
19:10:33 [ERROR] Failed to initialize wgpu RequestDevice(RequestDeviceError)
[hevc_vaapi @ 0x7faf601a6080] No usable encoding entrypoint found for profile VAProfileHEVCMain (17).
19:10:33 [ERROR] [hevc_vaapi @ 0x7faf601a6080] No usable encoding entrypoint found for profile VAProfileHEVCMain (17).
[aac @ 0x7faf61b65d80] Qavg: nan
[mov,mp4,m4a,3gp,3g2,mj2 @ 0x7faf600ebe80] st: 0 edit list: 1 Missing key frame while searching for timestamp: 1000
19:10:33 [WARN] [mov,mp4,m4a,3gp,3g2,mj2 @ 0x7faf600ebe80] st: 0 edit list: 1 Missing key frame while searching for timestamp: 1000
[mov,mp4,m4a,3gp,3g2,mj2 @ 0x7faf600ebe80] st: 0 edit list 1 Cannot find an index entry before timestamp: 1000.
19:10:33 [WARN] [mov,mp4,m4a,3gp,3g2,mj2 @ 0x7faf600ebe80] st: 0 edit list 1 Cannot find an index entry before timestamp: 1000.
19:10:44 [ERROR] thread '<unnamed>' panicked at 'Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))': /root/.cargo/git/checkouts/ocl-51b7c5264cbf134c/d0f4b61/ocl/src/standard/platform.rs:49
   0: <unknown>
   1: <unknown>
   2: <unknown>
   3: <unknown>
   4: <unknown>
   5: <unknown>
   6: <unknown>
   7: <unknown>
   8: <unknown>
   9: <unknown>
  10: <unknown>
  11: <unknown>
  12: <unknown>
  13: <unknown>
  14: <unknown>
  15: <unknown>
  16: <unknown>
  17: <unknown>
  18: <unknown>
  19: <unknown>
  20: <unknown>
  21: <unknown>
  22: start_thread
  23: clone

19:10:44 [ERROR] Failed to initialize OpenCL Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))
19:10:44 [ERROR] Failed to initialize wgpu RequestDevice(RequestDeviceError)
19:10:55 [ERROR] thread '<unnamed>' panicked at 'Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))': /root/.cargo/git/checkouts/ocl-51b7c5264cbf134c/d0f4b61/ocl/src/standard/platform.rs:49
   0: <unknown>
   1: <unknown>
   2: <unknown>
   3: <unknown>
   4: <unknown>
   5: <unknown>
   6: <unknown>
   7: <unknown>
   8: <unknown>
   9: <unknown>
  10: <unknown>
  11: <unknown>
  12: <unknown>
  13: <unknown>
  14: <unknown>
  15: <unknown>
  16: <unknown>
  17: <unknown>
  18: <unknown>
  19: <unknown>
  20: <unknown>
  21: <unknown>
  22: start_thread
  23: clone

19:10:55 [ERROR] Failed to initialize OpenCL Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))
19:10:55 [ERROR] Failed to initialize wgpu RequestDevice(RequestDeviceError)
[hevc_vaapi @ 0x7faf61b7b400] No usable encoding entrypoint found for profile VAProfileHEVCMain (17).
19:10:55 [ERROR] [hevc_vaapi @ 0x7faf61b7b400] No usable encoding entrypoint found for profile VAProfileHEVCMain (17).
[aac @ 0x7faf61b4c300] Qavg: nan
[mov,mp4,m4a,3gp,3g2,mj2 @ 0x7faf600ebe80] st: 0 edit list: 1 Missing key frame while searching for timestamp: 1000
19:10:55 [WARN] [mov,mp4,m4a,3gp,3g2,mj2 @ 0x7faf600ebe80] st: 0 edit list: 1 Missing key frame while searching for timestamp: 1000
[mov,mp4,m4a,3gp,3g2,mj2 @ 0x7faf600ebe80] st: 0 edit list 1 Cannot find an index entry before timestamp: 1000.
19:10:55 [WARN] [mov,mp4,m4a,3gp,3g2,mj2 @ 0x7faf600ebe80] st: 0 edit list 1 Cannot find an index entry before timestamp: 1000.
libva info: VA-API version 1.10.0
libva info: Trying to open /usr/lib/x86_64-linux-gnu/dri/iHD_drv_video.so
libva info: Found init function __vaDriverInit_1_10
libva info: va_openDriver() returns 0
[h264 @ 0x7faf604b9940] Failed setup for format vdpau: hwaccel initialisation returned error.
19:10:55 [ERROR] [h264 @ 0x7faf604b9940] Failed setup for format vdpau: hwaccel initialisation returned error.
19:11:06 [ERROR] thread '<unnamed>' panicked at 'Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))': /root/.cargo/git/checkouts/ocl-51b7c5264cbf134c/d0f4b61/ocl/src/standard/platform.rs:49
   0: <unknown>
   1: <unknown>
   2: <unknown>
   3: <unknown>
   4: <unknown>
   5: <unknown>
   6: <unknown>
   7: <unknown>
   8: <unknown>
   9: <unknown>
  10: <unknown>
  11: <unknown>
  12: <unknown>
  13: <unknown>
  14: <unknown>
  15: <unknown>
  16: <unknown>
  17: <unknown>
  18: <unknown>
  19: <unknown>
  20: <unknown>
  21: <unknown>
  22: start_thread
  23: clone

19:11:06 [ERROR] Failed to initialize OpenCL Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))
19:11:06 [ERROR] Failed to initialize wgpu RequestDevice(RequestDeviceError)
19:11:17 [ERROR] thread '<unnamed>' panicked at 'Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))': /root/.cargo/git/checkouts/ocl-51b7c5264cbf134c/d0f4b61/ocl/src/standard/platform.rs:49
   0: <unknown>
   1: <unknown>
   2: <unknown>
   3: <unknown>
   4: <unknown>
   5: <unknown>
   6: <unknown>
   7: <unknown>
   8: <unknown>
   9: <unknown>
  10: <unknown>
  11: <unknown>
  12: <unknown>
  13: <unknown>
  14: <unknown>
  15: <unknown>
  16: <unknown>
  17: <unknown>
  18: <unknown>
  19: <unknown>
  20: <unknown>
  21: <unknown>
  22: start_thread
  23: clone

19:11:17 [ERROR] Failed to initialize OpenCL Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))
19:11:17 [ERROR] Failed to initialize wgpu RequestDevice(RequestDeviceError)
19:11:27 [ERROR] thread '<unnamed>' panicked at 'Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))': /root/.cargo/git/checkouts/ocl-51b7c5264cbf134c/d0f4b61/ocl/src/standard/platform.rs:49
   0: <unknown>
```





 ~/usrbin/Gyroflow/gyroflow \
 --out-params "{ 'codec': 'H.265/HEVC', 'bitrate': 150, 'use_gpu': false, 'audio': true }" \
 --preset "{ 'version': 2, 'stabilization': { 'fov': 1.5 } }" \
 C0051.MP4



```
~/usrbin/Gyroflow/gyroflow \
 --out-params '{ "codec": "H.265/HEVC", "bitrate": 150, "use_gpu": false, "audio": true }' \
 --preset '{ "version": 2, "stabilization": { "fov": 1.5 } }' \
 C0051.MP4
```

disable GPU:


```
madon@toshibalex:~/gyroflow $ ~/usrbin/Gyroflow/gyroflow \
 --out-params '{ "codec": "H.265/HEVC", "bitrate": 150, "use_gpu": false, "audio": true }' \
 --preset '{ "version": 2, "stabilization": { "fov": 1.5 } }' \
 C0051.MP4
 
 
 
MDK 0.20.0 (git 3dd65ad) - Multimedia Development Kit. Copyright (c) 2016-2023 WangBin(QtAV author) <wbsecg1 at gmail.com>
Build for: Linux x86_64; Clang16.0.0 (++20230306093126+ae37edf1486d-1~exp1~20230306213138.48)GCC4.2.1; libc++160000; 01:35:31 Mar  7 2023
19:26:29 [DEBUG] (1) gyroflow: [in main] Qt version: 6.4.2
19:26:29 [DEBUG] (1) gyroflow: Gyroflow 1.5.0 (gh1128)
19:26:29 [INFO] Videos: ["C0051.MP4"]
19:26:29 [INFO] Presets: ["{ \"version\": 2, \"stabilization\": { \"fov\": 1.5 } }"]
19:26:29 [INFO] Lens profiles directory: "/home/madon/usrbin/Gyroflow/camera_presets"
19:26:29 [INFO] Loaded 6390 lens profiles in 145.925ms
19:26:39 [ERROR] thread 'main' panicked at 'Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))': /root/.cargo/git/checkouts/ocl-51b7c5264cbf134c/d0f4b61/ocl/src/standard/platform.rs:49
   0: <unknown>
   1: <unknown>
   2: <unknown>
   3: <unknown>
   4: <unknown>
   5: <unknown>
   6: <unknown>
   7: <unknown>
   8: <unknown>
   9: <unknown>
  10: <unknown>
  11: <unknown>
  12: <unknown>
  13: main
  14: __libc_start_main
  15: <unknown>

19:26:39 [ERROR] Failed to initialize OpenCL Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))
MESA-INTEL: warning: Performance support disabled, consider sysctl dev.i915.perf_stream_paranoid=0

[src/cli.rs:413] &settings = {
    "maxSyncPoints": "3",
    "defaultOverwriteAction": "0",
    "previewResolution": "0",
    "r3dConvertFormat": "0",
    "exportMode": "0",
    "backgroundMode": "0",
    "smoothing-1-max_smoothness": "1",
    "marginPixels": "0.2",
    "defaultCodec": "1",
    "adaptiveZoom": "4",
    "sync_lpf": "0",
    "exportAudio": "true",
    "padWithBlack": "false",
    "parallelRenders": "1",
    "timePerSyncpoint": "1.5",
    "smoothing-1-second_pass": "1",
    "preserveOtherTracks": "false",
    "exeLocation": "/home/madon/usrbin/Gyroflow/gyroflow",
    "visibility": "4",
    "useGravityVectors": "false",
    "checkNegativeInitialOffset": "false",
    "showOF": "true",
    "syncSearchSize": "5",
    "smoothing-1-smoothness": "0.5",
    "y": "51",
    "renderBackground": "#111111",
    "showFeatures": "true",
    "theme": "1",
    "rightPanelSize": "340",
    "smoothingMethod": "1",
    "playSounds": "true",
    "keyframeDistance": "1",
    "videoSpeedAffectsSmoothing": "true",
    "gpudecode": "true",
    "featherPixels": "0.05",
    "smoothing-1-smoothness_roll": "0.5",
    "defaultSuffix": "_stabilized",
    "uiScaling": "2",
    "correctionAmount": "1",
    "height": "685",
    "initialOffset": "0",
    "width": "1366",
    "safeAreaGuide": "false",
    "croppingMode": "1",
    "leftPanelSize": "340",
    "r3dColorMode": "0",
    "smoothing-1-smoothness_pitch": "0.5",
    "videoSpeedAffectsZooming": "true",
    "processingResolution": "3",
    "smoothing-1-per_axis": "0",
    "lang": "en",
    "smoothing-1-trim_range_only": "0",
    "x": "0",
    "previewPipeline": "0",
    "zoomingMethod": "0",
    "smoothing-1-alpha_0_1s": "0.1",
    "timelineChart": "0",
    "smoothing-1-smoothness_yaw": "0.5",
    "experimentalAutoSyncPoints": "false",
}
[mov,mp4,m4a,3gp,3g2,mj2 @ 0x7f769c000c40] st: 0 edit list: 1 Missing key frame while searching for timestamp: 1000
19:26:39 [WARN] [mov,mp4,m4a,3gp,3g2,mj2 @ 0x7f769c000c40] st: 0 edit list: 1 Missing key frame while searching for timestamp: 1000
[mov,mp4,m4a,3gp,3g2,mj2 @ 0x7f769c000c40] st: 0 edit list 1 Cannot find an index entry before timestamp: 1000.
19:26:39 [WARN] [mov,mp4,m4a,3gp,3g2,mj2 @ 0x7f769c000c40] st: 0 edit list 1 Cannot find an index entry before timestamp: 1000.
19:26:40 [INFO] Loaded VideoInfo { duration_ms: 18240.000000000004, frame_count: 456, fps: 25.0, width: 3840, height: 2160, bitrate: 95.33500957489014 }
19:26:40 [INFO] CameraIdentifier {
    brand: "Sony",
    model: "ZV-E10",
    lens_model: "",
    lens_info: "825191e",
    focal_length: None,
    camera_setting: "",
    fps: 25000,
    video_width: 3840,
    video_height: 2160,
    additional: "",
    identifier: "sony-zv-e10-825191e-3840x2160@25000",
}
19:26:40 [INFO] [7eaeea89] Processing done
19:26:40 [INFO] Applying preset { "version": 2, "stabilization": { "fov": 1.5 } }
19:26:40 [INFO] [7eaeea89] Processing done
[mov,mp4,m4a,3gp,3g2,mj2 @ 0x7f769c0e6140] st: 0 edit list: 1 Missing key frame while searching for timestamp: 1000
19:26:40 [WARN] [mov,mp4,m4a,3gp,3g2,mj2 @ 0x7f769c0e6140] st: 0 edit list: 1 Missing key frame while searching for timestamp: 1000
[mov,mp4,m4a,3gp,3g2,mj2 @ 0x7f769c0e6140] st: 0 edit list 1 Cannot find an index entry before timestamp: 1000.
19:26:40 [WARN] [mov,mp4,m4a,3gp,3g2,mj2 @ 0x7f769c0e6140] st: 0 edit list 1 Cannot find an index entry before timestamp: 1000.
[AVHWDeviceContext @ 0x7f769c1a7600] cu->cuInit(0) failed19:26:40 [ERROR] [AVHWDeviceContext @ 0x7f769c1a7600] cu->cuInit(0) failed
 -> CUDA_ERROR_NO_DEVICE: no CUDA-capable device is detected19:26:40 [ERROR] -> CUDA_ERROR_NO_DEVICE: no CUDA-capable device is detected

19:26:40 [ERROR] 
19:26:50 [ERROR] thread '<unnamed>' panicked at 'Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))': /root/.cargo/git/checkouts/ocl-51b7c5264cbf134c/d0f4b61/ocl/src/standard/platform.rs:49
   0: <unknown>
   1: <unknown>
   2: <unknown>
   3: <unknown>
   4: <unknown>
   5: <unknown>
   6: <unknown>
   7: <unknown>
   8: <unknown>
   9: <unknown>
  10: <unknown>
  11: <unknown>
  12: <unknown>
  13: <unknown>
  14: <unknown>
  15: <unknown>
  16: <unknown>
  17: <unknown>
  18: <unknown>
  19: <unknown>
  20: <unknown>
  21: <unknown>
  22: start_thread
  23: clone

19:26:50 [ERROR] Failed to initialize OpenCL Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))
19:26:50 [ERROR] Failed to initialize wgpu RequestDevice(RequestDeviceError)
19:27:01 [ERROR] thread '<unnamed>' panicked at 'Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))': /root/.cargo/git/checkouts/ocl-51b7c5264cbf134c/d0f4b61/ocl/src/standard/platform.rs:49
   0: <unknown>
   1: <unknown>
   2: <unknown>
   3: <unknown>
   4: <unknown>
   5: <unknown>
   6: <unknown>
   7: <unknown>
   8: <unknown>
   9: <unknown>
  10: <unknown>
  11: <unknown>
  12: <unknown>
  13: <unknown>
  14: <unknown>
  15: <unknown>
  16: <unknown>
  17: <unknown>
  18: <unknown>
  19: <unknown>
  20: <unknown>
  21: <unknown>
  22: start_thread
  23: clone

19:27:01 [ERROR] Failed to initialize OpenCL Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))
19:27:01 [ERROR] Failed to initialize wgpu RequestDevice(RequestDeviceError)
19:27:12 [ERROR] thread '<unnamed>' panicked at 'Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))': /root/.cargo/git/checkouts/ocl-51b7c5264cbf134c/d0f4b61/ocl/src/standard/platform.rs:49
   0: <unknown>
   1: <unknown>
   2: <unknown>
   3: <unknown>
   4: <unknown>
   5: <unknown>
   6: <unknown>
   7: <unknown>
   8: <unknown>
   9: <unknown>
  10: <unknown>
  11: <unknown>
  12: <unknown>
  13: <unknown>
  14: <unknown>
  15: <unknown>
  16: <unknown>
  17: <unknown>
  18: <unknown>
  19: <unknown>
  20: <unknown>
  21: <unknown>
  22: start_thread
  23: clone

19:27:12 [ERROR] Failed to initialize OpenCL Platform::list: Error retrieving platform list: ApiWrapper(GetPlatformIdsPlatformListUnavailable(10))
19:27:12 [ERROR] Failed to initialize wgpu RequestDevice(RequestDeviceError)
x265 [info]: HEVC encoder version 3.5+20-17839cc0d
x265 [info]: build info [Linux][clang 13.0.0][64 bit] 8bit+10bit+12bit
x265 [info]: using cpu capabilities: MMX2 SSE2Fast LZCNT SSSE3 SSE4.2 AVX FMA3 BMI2 AVX2
x265 [info]: Main profile, Level-5.1 (High tier)
x265 [info]: Thread pool created using 4 threads
x265 [info]: Slices                              : 1
x265 [info]: frame threads / pool features       : 2 / wpp(34 rows)
x265 [warning]: VBV maxrate specified, but no bufsize, ignored
x265 [info]: Coding QT: max CU size, min CU size : 64 / 8
x265 [info]: Residual QT: max TU size, max depth : 32 / 1 inter / 1 intra
x265 [info]: ME / range / subpel / merge         : hex / 57 / 2 / 3
x265 [info]: Keyframe min / max / scenecut / bias  : 2 / 25 / 40 / 5.00 
x265 [info]: Lookahead / bframes / badapt        : 20 / 4 / 2
x265 [info]: b-pyramid / weightp / weightb       : 1 / 1 / 0
x265 [info]: References / ref-limit  cu / depth  : 3 / off / on
x265 [info]: AQ: mode / str / qg-size / cu-tree  : 2 / 1.0 / 32 / 1
x265 [info]: Rate Control / qCompress            : ABR-157286 kbps / 0.60
x265 [info]: tools: rd=3 psy-rd=2.00 early-skip rskip mode=1 signhide tmvp
x265 [info]: tools: b-intra strong-intra-smoothing lslices=8 deblock sao
19:27:13 [INFO] Queue:
19:27:13 [INFO] - [7eaeea89] C0051.MP4 -> C0051_stabilized.mp4, 3840x2160 25.000fps | H.265/HEVC 150 Mbps, Frames: 456, Status: Rendering 
 
⡃⠀ Rendering:                                                                Elapsed: 00:21:33
 
⡃⠀ Rendering:                                                                Elapsed: 00:21:33
[#################################################>]   455/456   ETA 3.2s    C0051_stabilized.mp4                                             19:48:02 [INFO] Done in 1293.228s
x265 [info]: frame I:     19, Avg QP:11.61  kb/s: 403056.28
x265 [info]: frame P:    127, Avg QP:14.16  kb/s: 218147.83
x265 [info]: frame B:    310, Avg QP:18.00  kb/s: 104089.33
x265 [info]: Weighted P-Frames: Y:29.1% UV:15.0%
x265 [info]: consecutive B-frames: 17.8% 18.5% 19.2% 22.6% 21.9% 

encoded 456 frames in 1250.52s (0.36 fps), 148312.58 kb/s, Avg QP:16.67
```
That creates a file:

C0051_stabilized.mp4




https://oscarliang.com/how-to-use-gyroflow-video-stabilization-tool-for-fpv/

The default FOV is 1 and it’s pretty good for almost all my flying, you can zoom out or zoom in depends on your taste, but zooming too far out you might see the black edges when the camera is moving too much.

Next is Smoothness, basically that’s how much stabilization is applied to your footage. It’s important that you don’t over do it, too much stabilization (too high in smoothness) actually makes FPV flying looks robotic and unnatural. I found 0.3-0.4 to be a good starting point for most of my freestyle flying.

fields of view (FOV)




First-person view (FPV), 
also known as remote-person view (RPV)


https://docs.gyroflow.xyz/app/getting-started/basic-usage/stabilization
FOV
Field Of View - this value can be though of as a zoom slider. For most use cases, it should stay at 1.0. With Dynamic Zooming enabled, the value of 1.0 will ensure that the stabilization uses the maximum possible pixels while not showing any black bars/sides.
If you increase it over 1, you'll zoom out the video and show the outer frame, you can use that to see what stabilization is doing.
If you decrease it below 1, you'll zoom in the footage.



 ~/usrbin/Gyroflow/gyroflow \
 --out-params '{ "codec": "H.265/HEVC", "bitrate": 150, "use_gpu": false, "audio": true }' \
 --preset '{ "version": 2, "stabilization": { "fov": 1.2 } }' \
 C0051.MP4
 
 
 
 ~/usrbin/Gyroflow/gyroflow \
 --out-params '{ "codec": "H.265/HEVC", "bitrate": 150, "use_gpu": false, "audio": true }' \
 --preset '{ "version": 2, "stabilization": { "fov": 1.0 } }' \
 C0051.MP4
 


# logs

note that the log files are in the install dir:

```
madon@toshibalex:~/usrbin/Gyroflow $ rg 'H.265/HEVC' 
gyroflow.log
137:21:10:45 [INFO] - [263bd245] C0051.MP4 -> C0051_stabilized.mp4, 3840x2160 25.000fps | H.265/HEVC 150 Mbps, Frames: 456, Status: Rendering 
```


# GPU

https://askubuntu.com/questions/5417/how-to-get-the-gpu-info






```
root@toshibalex:~# lshw -C display
  *-display                 
       description: VGA compatible controller
       product: Skylake GT2 [HD Graphics 520]
       vendor: Intel Corporation
       physical id: 2
       bus info: pci@0000:00:02.0
       version: 07
       width: 64 bits
       clock: 33MHz
       capabilities: pciexpress msi pm vga_controller bus_master cap_list rom
       configuration: driver=i915 latency=0
       resources: irq:128 memory:c0000000-c0ffffff memory:b0000000-bfffffff ioport:3000(size=64) memory:c0000-dffff
```


codecs:

 "H.264/AVC" | "H.265/HEVC" | "AV1"


```
madon@toshibalex:~/gyroflow_git $ rg codec
gyroflow/src/rendering/render_queue.rs
83:            "H.264/AVC" | "H.265/HEVC" | "AV1" => format!("{} {:.0} Mbps", self.codec, self.bitrate),
```


~/usrbin/Gyroflow/gyroflow \
 --out-params '{ "codec": "H.264/AVC", "bitrate": 150, "use_gpu": true, "audio": true }' \
 --preset '{ "version": 2, "stabilization": { "fov": 1.2 } }' \
 C0051.MP4
 
10:14:03 [ERROR] Failed to initialize wgpu RequestDevice(RequestDeviceError)
