---
date: '2017-12-03T03:10:00.001-0700'
tags: linux 
---


# xubuntu Xenial 16.04 on HP ZBook 15 G4 (1RQ75ET#ABF)
{:.no_toc}

* TOC
{:toc}

## The specs


http://store.hp.com/FranceStore/Merch/Product.aspx?id=1RQ75ET&opt=ABF&sel=NTB

HP ZBook 15 G4 - 15.6" FHD i7 16Go 256Go SSD + 1 To HDD NVIDIA® Quadro® M2200

## The problems

install was freezing
restart was freezing
brightness control did not work (with F5 F6)

## Some solutions

at boot time press F11 or F9 to access BIOS

install xubuntu without update (no network connection)

then go to Settings -> Software & Updates

install the updates
install the proprietary Nvidia driver and the proprietary Intel-Microcode driver listed in the proprietarty drivers,. 

```bash
lspci
```

now works, brightness workss, restart works.

