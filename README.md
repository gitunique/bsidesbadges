# BSides Canberra badges
Notes related to BSides Canberra badges and modifications

One of the highlights of attending BSides Canberra each year is getting the
badges. They are typically easy to mod and make use of your own projects.

This repo contains links to the original code provided on the badges and
pointers to useful tools and reference material.

## Badge images

MD5 (2016/bsides2016.bin) = 8918769f7d3fcd1bbfd82037b7693dd0
MD5 (2017/bsides2017.bin) = f6f7bab4fae8a6af55ffc80dd1f5c956

Backups of original badge images were made using the [esptool]
(https://github.com/espressif/esptool) and the same tool can be used to restore
these images.

### Backup image from badge
```
esptool.py --port /dev/tty.wchusbserial1420 \
           --baud 115200 \
	   read_flash 0x00000 0x400000 \
	   backup_image.bin
```

### Restore image to badge
```
esptool.py --port /dev/tty.wchusbserial1420 \
           --baud 115200 write_flash \
	   -fm dio 0x00000 \
	   ibackup_image.bin 
```
