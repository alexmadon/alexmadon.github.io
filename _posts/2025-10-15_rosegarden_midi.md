# when no sound

You have two main possibilities:
use laso
use jackd



## with alsa

https://askubuntu.com/questions/620375/how-do-i-configure-sound-in-rosegarden

You can ignore the warnings about needing Jack running.

What I now have running is MIDI file playback via Rosegarden and QSynth.

The process as of Ubuntu 17.10 is largely the same as here, but follow these steps:

    install QSynth apt-get install fluidsynth
    install a soundfont library apt-get install fluid-soundfont-gs
    configure QSynth to Enable MIDI Input by checking the box in Setup > MIDI
    configure QSynth to use alsa Audio Driver under Setup > Audio
    configure QSynth to use the soundfont under Setup > Soundfonts; point to /usr/share/sounds/sf2/FluidR3_GM.sf2 or your soundfont location
    allow QSynth to restart when it prompts you
    install Rosegarden apt-get install rosegarden
    with QSynth open, launch Rosegarden
    Tell Rosegarden to play through QSynth Studio > Manage MIDI Devices and set the General MIDI Device to whatever QSynth broadcasts as its MIDI input option, ie 129:0 Synth input port or similar.

Alex: in Rosegarden -> Edit -> Preferences -> audio: do NOT select any of the Jack options



## with jackd

also documnted here:

https://askubuntu.com/questions/620375/how-do-i-configure-sound-in-rosegarden
