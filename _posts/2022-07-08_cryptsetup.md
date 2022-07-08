# backup crypto crypted mount

https://www.cyberciti.biz/hardware/howto-linux-hard-disk-encryption-with-luks-cryptsetup-command/
Linux Unified Key Setup-on-disk-format (LUKS)
https://meet-unix.org/2017-04-14-fde_with_uefi.html
 
apt-get install cryptsetup

INIT:

1) insert disk, watch dmesg

[1623722.780898]  sdb: sdb1

2) change or create the partion of type 83 linux

3) create LuskContainer


cryptsetup luksFormat /dev/sdb1

4) create map to "backup1"
cryptsetup luksOpen /dev/sdb1 backup1


5) optional, confirm you see the map:

root@hp:~# ls -l /dev/mapper/backup1
lrwxrwxrwx 1 root root 7 Mar 22 12:02 /dev/mapper/backup1 -> ../dm-3

root@hp:~# cryptsetup -v status backup1
/dev/mapper/backup1 is active.
  type:    LUKS1
  cipher:  aes-xts-plain64
  keysize: 256 bits
  device:  /dev/sdb1
  offset:  4096 sectors
  size:    1953515520 sectors
  mode:    read/write
Command successful.


You can check the keys and headers:

cryptsetup luksDump /dev/sdb1 

LUKS header information for /dev/sdb1

Version:       	1
Cipher name:   	aes
Cipher mode:   	xts-plain64
Hash spec:     	sha256
Payload offset:	4096
MK bits:       	256
MK digest:     	bb 94 6f 1c 5a ae 25 6a e7 eb 65 84 d7 24 97 86 a5 fe 8a 76 
MK salt:       	7a 21 59 32 b7 3a 7a e0 c6 66 7b 25 29 b4 4a 5b 
               	28 24 57 5a 60 f2 86 1b 3b 83 83 55 23 f7 b9 ba 
MK iterations: 	321500
UUID:          	ab7ef56e-24f3-4bfe-8fa4-61e13890f1d4

Key Slot 0: ENABLED
	Iterations:         	2560000
	Salt:               	eb 6e 5a 66 40 cf 1a b8 b2 f4 2d a7 3c af ff a1 
	                      	18 05 3e 25 60 92 60 dc 47 6d 19 b5 e8 45 b3 cd 
	Key material offset:	8
	AF stripes:            	4000
Key Slot 1: DISABLED
Key Slot 2: DISABLED
Key Slot 3: DISABLED
Key Slot 4: DISABLED
Key Slot 5: DISABLED
Key Slot 6: DISABLED
Key Slot 7: DISABLED


6) OPTIONAL put zeros:

dd if=/dev/zero of=/dev/mapper/backup1 status=progress

(WARNING: can take hours !!!!)

7) format:

mkfs.ext4 /dev/mapper/backup1


8)
mkdir /mnt
mount /dev/mapper/backup1 /mnt



9) do the sync


10)  UNMOUNT

umount /mnt
cryptsetup luksClose backup1

11) NEXT TIMES

cryptsetup luksOpen /dev/sdb1 backup1
mount /dev/mapper/backup1 /mnt
