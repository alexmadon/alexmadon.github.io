How To Automount File Systems on Linux

https://www.linuxbabe.com/desktop-linux/how-to-automount-file-systems-on-linux

madon@toshibalex:~ $ ssh nipogi

su -

root@nipogi:~# blkid
/dev/sdb1: UUID="4d5da0d1-c2d8-49cc-808a-c700a68def7c" BLOCK_SIZE="4096" TYPE="ext4" PARTUUID="26655201-5a8c-b243-9594-305fe9aa1bf4"
/dev/sda2: UUID="bbbe6e8b-9437-45c2-a088-eaae6e772ade" BLOCK_SIZE="4096" TYPE="ext4" PARTUUID="a8613bdb-f0e8-47c4-92a5-976fff03daf8"
/dev/sda3: UUID="3bcd9982-04d6-4ade-ba86-5b2a4a8d3b84" TYPE="swap" PARTUUID="54cb6ef9-3e3e-4651-962a-e2c08816d098"
/dev/sda1: UUID="A2B9-B586" BLOCK_SIZE="512" TYPE="vfat" PARTUUID="c294cd12-a4f6-4d87-af66-aa460410136d"


root@nipogi:~# mkdir /mnt/sandisk4tb1

root@nipogi:~# tail /etc/fstab 
UUID=4d5da0d1-c2d8-49cc-808a-c700a68def7c  /mnt/sandisk4tb1  ext4  defaults  0  2


root@nipogi:~# mount -a
montage : (astuce) votre fstab a été modifié mais systemd utilise encore
       l'ancienne version ; utilisez « systemctl daemon-reload » pour recharger.
root@nipogi:~# systemctl daemon-reload
root@nipogi:~# mount -a
root@nipogi:~# mount
.....
/dev/sdb1 on /mnt/sandisk4tb1 type ext4 (rw,relatime,stripe=256)
