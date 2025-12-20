# scanner Canon CanoScan Lide 300

scanner Canon CanoScan Lide 300 is supported in Sane
http://www.sane-project.org/sane-mfgs.html
CanoScan LiDE 300 	USB 	0x04a9/0x1913 	Complete 	All resolutions supported (up to 2400DPI) 	pixma
(0.28.6) 	sane-pixma


http://www.sane-project.org/man/sane-pixma.5.html
https://www.hamrick.com/vuescan/canon_lide_300.html#technical-information

the scanner has a lock open/close button on the back

The scanner does not have a power switch. The scanner turns on when the USB cable is connect to the computer.

when you plus the scanner through USB, `dmesg` will show:


```
[320937.304049] usb 1-3: new high-speed USB device number 12 using xhci_hcd
[320937.453492] usb 1-3: New USB device found, idVendor=04a9, idProduct=1913, bcdDevice= 1.00
[320937.453514] usb 1-3: New USB device strings: Mfr=1, Product=2, SerialNumber=3
[320937.453525] usb 1-3: Product: LiDE 300
[320937.453531] usb 1-3: Manufacturer: Canon
[320937.453537] usb 1-3: SerialNumber: 59D4C1
```


When you start xsane, it will detect the scanner and offer three possibilities:


pixma escl airscan
https://lists.debian.org/debian-user/2021/01/msg00300.html



# LOCK

Always release the scanner lock before connecting the scanner to a computer.
Running the scanner while it is locked will damage the scanner.

Precautions for Safe Transport of Scanner
