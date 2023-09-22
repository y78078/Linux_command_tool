# mount
## wic ps. 
### sudo mount -o loop,offset=$((16384*512)) imx-image-full-imx8qxpmmek.rootfs.wic mmcblk0p1/
note 16384 checked by fdisk

### example
#!/bin/sh -e

mkdir -p mmcblk0p1

mkdir -p mmcblk0p2

sudo mount -o loop,offset=$((196608*512)) imx-image-full-imx8qxpmmek.rootfs.wic mmcblk0p2/

cd mmcblk0p2

sudo cp ../systemd-journal-flush.service lib/systemd/system/systemd-journal-flush.service

sudo cp ../systemd-journald.service lib/systemd/system/systemd-journald.service

sudo cp ../systemd-udevd.service lib/systemd/system/systemd-udevd.service

sudo mv lib/modules/5.10.72-lts-5.10.y+g41791c47cb17 lib/modules/5.10.72-lts-5.10.y+

sync

cd ..

sudo umount mmcblk0p2

sleep 0.5

sudo mount -o loop,offset=$((16384*512)),sizelimit=85M imx-image-full-imx8qxpmmek.rootfs.wic mmcblk0p1/

cd mmcblk0p1

sudo rm -rf Image

sudo cp ../Image .

sync

cd ..

sudo umount mmcblk0p1

exit 0

