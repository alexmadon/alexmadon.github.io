Liseuse vivlio light


# connect using usb C

```
dmesg
[202949.407144] usb 1-3: Manufacturer: Obreey

[202949.407150] usb 1-3: SerialNumber: 20080411
[202949.414936] usb-storage 1-3:1.0: USB Mass Storage device detected
[202949.415786] scsi host2: usb-storage 1-3:1.0
[202949.592150] usb 1-3: USB disconnect, device number 9
[202965.466657] usb 1-3: new high-speed USB device number 10 using xhci_hcd
[202965.619394] usb 1-3: New USB device found, idVendor=fffe, idProduct=0001, bcdDevice= 1.01
[202965.619415] usb 1-3: New USB device strings: Mfr=2, Product=3, SerialNumber=4
[202965.619424] usb 1-3: Product: Vivlio

[202965.619430] usb 1-3: Manufacturer: Obreey

[202965.619436] usb 1-3: SerialNumber: LG4E1100162900WV01P4
[202965.621724] usb-storage 1-3:1.0: USB Mass Storage device detected
[202965.622276] scsi host2: usb-storage 1-3:1.0
[202966.655181] scsi 2:0:0:0: Direct-Access     USB-FS   PocketBook       0310 PQ: 0 ANSI: 2
[202966.656048] sd 2:0:0:0: Attached scsi generic sg1 type 0
[202966.656369] sd 2:0:0:0: Power-on or device reset occurred
[202966.656846] sd 2:0:0:0: [sdb] 13586432 512-byte logical blocks: (6.96 GB/6.48 GiB)
[202966.657049] sd 2:0:0:0: [sdb] Write Protect is off
[202966.657058] sd 2:0:0:0: [sdb] Mode Sense: 0f 00 00 00
[202966.657332] sd 2:0:0:0: [sdb] Write cache: enabled, read cache: enabled, doesn't support DPO or FUA
[202966.665961]  sdb:
[202966.666962] sd 2:0:0:0: [sdb] Attached SCSI removable disk
```

# mount

```
root@toshibalex:~# mount /dev/sdb /mnt
root@toshibalex:~# ls /mnt
applications  autorun.inf  Downloads  Manual-Vivlio-Light-Fr.epub  Photo  system
```



```
root@toshibalex:/mnt# find
.
./system
./system/manuals
./system/manuals/Manual-Vivlio-Light-En.epub
./system/manuals/Manual-Vivlio-Light-Es.epub
./system/manuals/Manual-Vivlio-Light-Fr.epub
./system/manuals/Manual-Vivlio-Light-Nl.epub
./system/etc
./system/etc/hosts
./system/bin
./system/dictionaries
./system/adobe
./system/adobe/hyphenDicts
./system/adobe/hyphenDicts/hyph_el.dic
./system/adobe/hyphenDicts/hyph_ro.dic
./system/adobe/hyphenDicts/hyph_fr.dic
./system/adobe/hyphenDicts/hyph_bg.dic
./system/adobe/hyphenDicts/hyph_fi.dic
./system/adobe/hyphenDicts/hyph_cs.dic
./system/adobe/hyphenDicts/hyph_pl.dic
./system/adobe/hyphenDicts/hyph_ca.dic
./system/adobe/hyphenDicts/hyph_ru.dic
./system/adobe/hyphenDicts/hyph_ku.dic
./system/adobe/hyphenDicts/hyph_uk.dic
./system/adobe/hyphenDicts/hyph_id.dic
./system/adobe/hyphenDicts/hyph_de.dic
./system/adobe/hyphenDicts/hyph_no.dic
./system/adobe/hyphenDicts/hyph_da.dic
./system/adobe/hyphenDicts/hyph_nl.dic
./system/adobe/hyphenDicts/hyph_sk.dic
./system/adobe/hyphenDicts/hyph_sl.dic
./system/adobe/hyphenDicts/hyph_tr.dic
./system/adobe/hyphenDicts/hyph_en.dic
./system/adobe/hyphenDicts/hyph_lt.dic
./system/adobe/hyphenDicts/hyph_is.dic
./system/adobe/hyphenDicts/hyph_gl.dic
./system/adobe/hyphenDicts/hyph_sv.dic
./system/adobe/hyphenDicts/hyph_it.dic
./system/adobe/hyphenDicts/hyph_pt.dic
./system/adobe/hyphenDicts/hyph_ia.dic
./system/adobe/hyphenDicts/hyph_eo.dic
./system/adobe/hyphenDicts/hyph_hu.dic
./system/adobe/hyphenDicts/hyph_af.dic
./system/adobe/hyphenDicts/hyph_es.dic
./system/adobe/hyphenDicts/hyph_hr.dic
./system/adobe/fonts
./system/adobe/fonts/AdobeHeitiStd-Regular.otf.lnk
./system/adobe/fonts/PTSerif-Italic.ttf.lnk
./system/adobe/fonts/CourierStd-Bold.otf.lnk
./system/adobe/fonts/AdobeMingStd-Light.otf.lnk
./system/adobe/fonts/CourierStd.otf.lnk
./system/adobe/fonts/MyriadPro-Bold.otf.lnk
./system/adobe/fonts/CourierStd-BoldOblique.otf.lnk
./system/adobe/fonts/PTSerif-Bold.ttf.lnk
./system/adobe/fonts/MinionPro-Bold.otf.lnk
./system/adobe/fonts/PTSerif.ttf.lnk
./system/adobe/fonts/PTSerif-BoldItalic.ttf.lnk
./system/adobe/fonts/MinionPro-Regular.otf.lnk
./system/adobe/fonts/AdobeMyungjoStd-Medium.otf.lnk
./system/adobe/fonts/MyriadPro-It.otf.lnk
./system/adobe/fonts/MinionPro-It.otf.lnk
./system/adobe/fonts/RyoGothicPlusN-Medium.otf.lnk
./system/adobe/fonts/MyriadPro-Regular.otf.lnk
./system/adobe/fonts/MinionPro-BoldIt.otf.lnk
./system/adobe/fonts/MyriadPro-BoldIt.otf.lnk
./system/adobe/fonts/SymbolStd.otf.lnk
./system/adobe/fonts/CourierStd-Oblique.otf.lnk
./system/themes
./system/pbdicts
./system/pbdicts/pbdicts.db
./system/cache
./system/cache/fontconfig
./system/cache/fontconfig/9e22a7339dc542fc8ce4bdd90159af0a-arm-obreey-linux-gnueabi.cache-7
./system/cache/fontconfig/CACHEDIR.TAG
./system/cache/fontconfig/eefb7aa1c0d300d44dd71108345cbe4c-arm-obreey-linux-gnueabi.cache-7
./system/cache/desktop
./system/cache/desktop/1
./system/cache/desktop/1/Manual-Vivlio-Light-Fr.epub_262x393.png
./system/cache/desktop/1/Manual-Vivlio-Light-Fr.epub_404x609.png
./system/cache/desktop/1/Manual-Vivlio-Light-Fr.epub_212x320.png
./system/cache/desktop/cache.dat
./system/cache/desktop/cache.dat.back
./system/cache/desktop_data_bookstore
./system/cache/desktop_data_bookstore/recommended_4.jpg
./system/cache/desktop_data_bookstore/recommended_2.jpg
./system/cache/desktop_data_bookstore/recommended_3.jpg
./system/cache/desktop_data_bookstore/recommended_1.jpg
./system/cache/desktop_data_bookstore/recommended_5.jpg
./system/cache/desktop_data_bookstore/news_1.jpg
./system/cache/desktop_data_bookstore/news_2.jpg
./system/cache/desktop_data_bookstore/news_3.jpg
./system/cache/desktop_data_bookstore/news_4.jpg
./system/cache/desktop_data_bookstore/news_5.jpg
./system/cache/desktop_data_bookstore/bestsellers_1.jpg
./system/cache/desktop_data_bookstore/bestsellers_2.jpg
./system/cache/desktop_data_bookstore/bestsellers_3.jpg
./system/cache/desktop_data_bookstore/bestsellers_4.jpg
./system/cache/desktop_data_bookstore/bestsellers_5.jpg
./system/state
./system/state/storage
./system/state/storage/browser
./system/state/storage/browser/blob_storage
./system/state/storage/browser/blob_storage/6e443e86-c02e-43e2-a9d3-96ef2c7caf53
./system/state/storage/browser/Cookies
./system/state/storage/browser/Cookies-journal
./system/state/storage/browser/Visited Links
./system/state/storage/browser/Local Storage
./system/state/storage/browser/Local Storage/leveldb
./system/state/storage/browser/Local Storage/leveldb/LOG
./system/state/storage/browser/Local Storage/leveldb/LOCK
./system/state/storage/browser/Local Storage/leveldb/LOG.old
./system/state/storage/browser/Local Storage/leveldb/CURRENT
./system/state/storage/browser/Local Storage/leveldb/000009.ldb
./system/state/storage/browser/Local Storage/leveldb/000010.log
./system/state/storage/browser/Local Storage/leveldb/MANIFEST-000008
./system/state/storage/browser/IndexedDB
./system/state/storage/browser/IndexedDB/https_shop.vivlio.com_0.indexeddb.leveldb
./system/state/storage/browser/IndexedDB/https_shop.vivlio.com_0.indexeddb.leveldb/LOG
./system/state/storage/browser/IndexedDB/https_shop.vivlio.com_0.indexeddb.leveldb/LOCK
./system/state/storage/browser/IndexedDB/https_shop.vivlio.com_0.indexeddb.leveldb/LOG.old
./system/state/storage/browser/IndexedDB/https_shop.vivlio.com_0.indexeddb.leveldb/CURRENT
./system/state/storage/browser/IndexedDB/https_shop.vivlio.com_0.indexeddb.leveldb/000005.ldb
./system/state/storage/browser/IndexedDB/https_shop.vivlio.com_0.indexeddb.leveldb/000006.log
./system/state/storage/browser/IndexedDB/https_shop.vivlio.com_0.indexeddb.leveldb/MANIFEST-000004
./system/state/storage/browser/QuotaManager
./system/state/storage/browser/TransportSecurity
./system/state/storage/browser/QuotaManager-journal
./system/state/cache
./system/state/cache/browser
./system/state/cache/browser/Cache
./system/state/cache/browser/Cache/index
./system/state/cache/browser/Cache/data_0
./system/state/cache/browser/Cache/data_1
./system/state/cache/browser/Cache/data_2
./system/state/cache/browser/Cache/data_3
./system/state/cache/browser/Cache/f_000003
./system/state/cache/browser/Cache/f_000002
./system/state/cache/browser/Cache/f_000004
./system/state/cache/browser/Cache/f_000005
./system/state/cache/browser/Cache/f_000006
./system/state/cache/browser/Cache/f_000007
./system/state/cache/browser/Cache/f_000008
./system/state/cache/browser/Cache/f_000009
./system/state/cache/browser/Cache/f_00000a
./system/state/cache/browser/Cache/f_00000b
./system/state/cache/browser/Cache/f_00000c
./system/state/cache/browser/Cache/f_00000d
./system/state/cache/browser/Cache/f_00000e
./system/state/cache/browser/Cache/f_00000f
./system/state/cache/browser/Cache/f_000010
./system/state/cache/browser/Cache/f_000011
./system/state/cache/browser/Cache/f_000012
./system/state/cache/browser/Cache/f_000013
./system/state/cache/browser/Cache/f_000014
./system/state/cache/browser/Cache/f_000015
./system/state/cache/browser/Cache/f_000016
./system/state/browser
./system/config
./system/config/fbreader.cfg
./system/config/global.cfg
./system/config/global.cfg.back
./system/config/audiobooks
./system/config/browser_ota.cfg
./system/config/desktop
./system/config/desktop/apps.json
./system/config/desktop/view.json
./system/config/desktop/hash.txt
./system/config/desktop/hash.txt.back
./system/config/pbcloud.cfg
./system/config/books.db
./system/config/tea_authorization
./system/config/tea_authorization/config.cfg
./system/config/tea_authorization/config.cfg.back
./system/config/tea_authorization/token.json
./system/config/pbcloud.cfg.back
./system/config/.pbcloud_token
./system/config/.pbcloud_token.back
./system/config/.tea_lcp
./system/config/.tea_lcp.back
./system/config/desktop_data.cfg
./system/config/desktop_data.cfg.back
./system/device629.ico
./system/favorite
./system/language
./system/language/keyboard
./system/language/keyboard/RU.extkbd
./system/language/keyboard/IT.extkbd
./system/language/keyboard/EN.extkbd
./system/language/keyboard/UA.extkbd
./system/widgets
./system/reader
./system/reader/settings-fb2-dflt.ini
./system/reader/fb2.css
./system/reader/linespacing.cfg
./system/reader/mathml
./system/reader/mathml/MathJax.js
./system/reader/html.css
./system/reader/notes.css
./system/reader/settings-rtf-dflt.ini
./system/reader/settings-adobe-epub-dflt.ini
./system/reader/margins.cfg
./system/reader/rtf.css
./system/reader/settings-app-dflt.ini
./system/reader/settings-prf-dflt.ini
./system/logo
./system/logo/bootlogo
./system/logo/offlogo
./system/Certificates
./system/cover_chache
./system/cover_chache/1
./system/cover_chache/1/Photo
./system/cover_chache/1/Photo/FondEcranTouchHDplus1.png.png
./system/cover_chache/1/Photo/FondEcranTouchHDplus2.png.png
./system/cover_chache/1/Photo/image-EN2.png.png
./system/cover_chache/1/Photo/image-FR1.png.png
./system/cover_chache/1/Photo/image-FR2.png.png
./system/cover_chache/1/Photo/image-NL.png.png
./system/cover_chache/1/Manual-Vivlio-Light-Fr.epub.png
./system/cover_chache/by_resource_id
./system/cover_chache/by_resource_id/34343637626637652d336234322d343661622d393136652d613763643064636239303164.png
./system/cover_chache/by_resource_id/64643133303131332d666464382d343334652d396639332d303238663664323539633565.png
./system/cover_chache/by_resource_id/32343830626137662d396561322d343939332d393863632d333637626630623638346566.png
./system/fonts
./system/explorer-3
./system/explorer-3/explorer-3.db.lock
./system/explorer-3/explorer-3.db
./system/explorer-3/explorer-3.db-wal
./system/explorer-3/explorer-3.db-shm
./system/explorer-3/settings.cfg
./system/explorer-3/settings.cfg.back
./system/.pocketbook
./system/player-2
./system/player-2/player-2.db.lock
./system/player-2/player-2.db
./system/player-2/player-2.db-wal
./system/player-2/player-2.db-shm
./system/timezone
./system/browser.sqlite
./system/tts
./system/last_update_check
./system/pbcloud_sync_covers_lock
./applications
./autorun.inf
./.adobe-digital-editions
./.adobe-digital-editions/device.xml
./Manual-Vivlio-Light-Fr.epub
./.adobe-hidden-files
./Photo
./Photo/FondEcranTouchHDplus1.png
./Photo/FondEcranTouchHDplus2.png
./Photo/image-EN2.png
./Photo/image-FR1.png
./Photo/image-FR2.png
./Photo/image-NL.png
./Downloads
```

# put you files in /Downloads

