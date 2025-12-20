In cups find by IP.
Ip can be printed from printer: configuration -> print
192.168.1.24
MAC 00:15:99:DA:AF:74
ipp://192.168.1.24/ipp/

http://192.168.1.24/ipp

if that does not work, restart printer
http://192.168.1.24


SEC001599DAAF74
https://192.168.1.24/sws/index.html

http://192.168.1.24/sws/index.html


you may need to clean cups daemon

stop cups;
root@toshibalex:/etc/cups# /etc/init.d/cups stop
stop web daemon
root@toshibalex:/etc/cups#  /etc/init.d/cups-browsed stop

root@toshibalex:/etc/cups# grep SEC ./cupsd.conf
root@toshibalex:/etc/cups# grep -r SEC *
printers.conf:<Printer Samsung_ML_371x_Series_SEC001599DAAF74>
printers.conf:Info Samsung_ML_371x_Series_SEC001599DAAF74
printers.conf:DeviceURI ipp://SEC001599DAAF74.local:631/
printers.conf.O:<Printer Samsung_ML_371x_Series_SEC001599DAAF74>
printers.conf.O:Info Samsung_ML_371x_Series_SEC001599DAAF74
printers.conf.O:DeviceURI ipp://SEC001599DAAF74.local:631/
printers.conf.O:<Printer Samsung_ML_371x_Series_SEC001599DAAF74@SEC001599DAAF74.local>
printers.conf.O:Info Samsung_ML_371x_Series_SEC001599DAAF74
printers.conf.O:DeviceURI implicitclass://Samsung_ML_371x_Series_SEC001599DAAF74%40SEC001599DAAF74.local/
root@toshibalex:/etc/cups# mv printers.conf
printers.conf    printers.conf.O  
root@toshibalex:/etc/cups# mv printers.conf printers.conf.old1
root@toshibalex:/etc/cups# diffuse  printers.conf.O printers.conf.old1
root@toshibalex:/etc/cups# mv printers.conf.O printers.conf.old2
root@toshibalex:/etc/cups# /etc/init.d/cups start
Starting cups (via systemctl): cups.service.
root@toshibalex:/etc/cups# 
