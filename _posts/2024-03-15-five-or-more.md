xdotool getactivewindow windowsize 50% 50%
madon@toshibalex:~ $ xwininfo -root -tree | grep -i five -C8

xwininfo -root -tree | grep -i five 
     0x5600001 "Five or More": ("five-or-more" "Five-or-more")  10x10+10+10  +10+10
        0x5a0013e "2024-03-15-five-or-more.md - GNU Emacs at toshibalex": ("emacs" "Emacs")  676x608+5+29  +129+146
        0x5600007 "Five or More": ("five-or-more" "Five-or-more")  640x391+0+0  +32+4


xdotool   windowsize 0x5600007 50% 50%



https://www.reddit.com/r/linuxquestions/comments/qmnhfu/what_setting_controls_the_window_size_and/



Hmm, this worked for me: gsettings set org.gnome.calculator window-position '(100, 100)'. Although once you close the calculator, it stores its last position again. I'm not sure how to set the window size with gsettings.

Another option would be to use a program like xdotool to move and resize it: 

xdotool search --onlyvisible --class 'Gnome-calculator' windowmove 100 100 windowsize 1000 500


xdotool search --onlyvisible --class 'five-or-more' windowmove 10% 10% windowsize 50% 80%
