To list microphones in Debian using PulseAudio, use
pactl list sources short for a concise list or pactl list sources for detailed information. The {Link: PulseAudio Volume Control (pavucontrol) https://wiki.debian.org/PulseAudio} GUI tool, installable via sudo apt install pavucontrol, provides a user-friendly interface to manage input devices. 
Key Commands for Listing Microphones (PulseAudio/ALSA)

    pactl list sources short: Lists all available PulseAudio input sources (microphones/monitors) concisely.
    pactl list sources: Provides detailed information on all sources.
    arecord -l: Lists available capture devices (microphones) directly from ALSA.
    pavucontrol: Opens the PulseAudio mixer GUI to see input devices, volumes, and select the active mic. 

Common Troubleshooting
If the microphone is not working, ensure pulseaudio is installed (sudo apt install pulseaudio). If needed, you can install alsa-ucm-conf and sof-firmware. 


```
adon@toshibalex:~ $ pactl list sources
Source #40
	State: SUSPENDED
	Name: auto_null.monitor
	Description: Monitor of Dummy Output
	Driver: PipeWire
	Sample Specification: float32le 2ch 48000Hz
	Channel Map: front-left,front-right
	Owner Module: 4294967295
	Mute: no
	Volume: front-left: 65536 / 100% / 0.00 dB,   front-right: 65536 / 100% / 0.00 dB
	        balance 0.00
	Base Volume: 65536 / 100% / 0.00 dB
	Monitor of Sink: auto_null
	Latency: 0 usec, configured 0 usec
	Flags: DECIBEL_VOLUME LATENCY 
	Properties:
		node.name = "auto_null"
		device.description = "Dummy Output"
		audio.rate = "48000"
		audio.channels = "2"
		audio.position = "FL,FR"
		media.class = "Audio/Sink"
		factory.name = "support.null-audio-sink"
		node.virtual = "true"
		monitor.channel-volumes = "true"
		factory.id = "18"
		clock.quantum-limit = "8192"
		client.id = "31"
		node.driver = "true"
		factory.mode = "merge"
		audio.adapt.follower = ""
		library.name = "audioconvert/libspa-audioconvert"
		object.id = "40"
		object.serial = "40"
		device.class = "monitor"
	Formats:
		pcm
```

record during 20 seconds:

```
arecord -d 20 test-mic.wav
```

```
madon@toshibalex:~ $ pactl list sources
Source #40
	State: RUNNING
	Name: auto_null.monitor
	Description: Monitor of Dummy Output
	Driver: PipeWire
	Sample Specification: float32le 2ch 48000Hz
	Channel Map: front-left,front-right
	Owner Module: 4294967295
	Mute: no
	Volume: front-left: 65536 / 100% / 0.00 dB,   front-right: 65536 / 100% / 0.00 dB
	        balance 0.00
	Base Volume: 65536 / 100% / 0.00 dB
	Monitor of Sink: auto_null
	Latency: 0 usec, configured 0 usec
	Flags: DECIBEL_VOLUME LATENCY 
	Properties:
		node.name = "auto_null"
		device.description = "Dummy Output"
		audio.rate = "48000"
		audio.channels = "2"
		audio.position = "FL,FR"
		media.class = "Audio/Sink"
		factory.name = "support.null-audio-sink"
		node.virtual = "true"
		monitor.channel-volumes = "true"
		factory.id = "18"
		clock.quantum-limit = "8192"
		client.id = "31"
		node.driver = "true"
		factory.mode = "merge"
		audio.adapt.follower = ""
		library.name = "audioconvert/libspa-audioconvert"
		object.id = "40"
		object.serial = "40"
		device.class = "monitor"
	Formats:
		pcm
```


Common Solutions

    Laptop Internal Mic Fix: Internal microphones often appear as stereo but are mono. Mute one of the channels in alsamixer if it fails to work.
    USB/External Mic Check: If using a USB device, try a different port. For 3.5mm jacks, ensure it is fully inserted, as dust can cause issues.
    Debian 13 Backports: If you are using newer hardware on Debian 13 (Trixie), installing a newer kernel from backports may fix driver issues.
    Remove Conflicting Modules: If the microphone worked previously, check for recent updates breaking it. A common fix involves blacklisting snd_soc_skl in /etc/modprobe.d/. 

If the issue persists, run arecord -l to check if the system detects the hardware



```
madon@toshibalex:~ $ arecord -l
**** List of CAPTURE Hardware Devices ****
card 0: PCH [HDA Intel PCH], device 0: ALC255 Analog [ALC255 Analog]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
```
