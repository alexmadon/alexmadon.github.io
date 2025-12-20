

Q: How to set auto power on when a power failure?

A: Boot the mini pc and press"delete" key
- Enter into "BIOS Interface"
- Select"Boot"in the interface
- Select"Automatic power on"-Select"Enable"-Save and Exit.





Q: je ne sais pas comment accéder aux réglages du bios pour pouvoir booter sur cette clé

Il n'y a généralement pas besoin de modifier la configuraton du BIOS (plutôt sans doute ici un UEFI) pour démarrer sur un support externe. Sur tous les PC datant de moins de vingt ans une touche de fonction permet au démarrage de choisir le périphérique d'amorçage.


configuration - How do I enable auto-login in LightDM? - Ask Ubuntu
https://askubuntu.com/questions/51086/how-do-i-enable-auto-login-in-lightdm 

https://kodi.wiki/view/HOW-TO:Autostart_Kodi_for_Linux

check that:
which x-window-manager
points using symbolic link to xfwm4


# autlogin in LightDM
/etc/lightdm/lightdm.conf

```
[Seat:*]
autologin-user=madon
autologin-user-timeout=0
```


# luanch kodi

~/.config/autostart/kodi.desktop

[Desktop Entry]
Name=kodi
Exec=kodi



https://kodi.wiki/view/Web_interface
# start web server and control using android kore app

# no sound

in kodi, go to system -> audio -> output deveice: hdmi




# chinese hardware


https://www.aliexpress.com/item/32827493578.html I got this one, warehouse in Belgium, came in a week
this is how you install it https://www.rigacci.org/wiki/doku.php/doc/appunti/hardware/x96_mini

I got it for X265 basically
didn't want to use an expensive Pi 4 for a player
it was about 70 euros at the time
so I got this one and it works great
even has a remote :))
and I use it to power up some USB things too, since it's always on and low power
yes, and the remote works well in Kodi too

Amlogic S905W linux
Installing Armbian on Amlogic S905w Android TV Box
https://i12bretro.github.io/tutorials/0316.html
