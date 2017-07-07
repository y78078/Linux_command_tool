# Installing 32-bit libraries on Ubuntu 16.04 Xenial Xerus

## In Ubuntu 12.04
sudo apt-get install ia32-libs

## In Ubuntu 16.04
### Enable the i386 architecture (as root user):

dpkg --add-architecture i386

apt-get update

### Install 32-bit libraries (as root user):
apt-get install libc6:i386 libstdc++6:i386

### ia32-libs has been changed
Here's what worked

sudo apt-get install libgl1-mesa-dri:i386
sudo apt-get install ia32-libs-multiarch:i386

sudo apt-get install ia32-libs-multiarch

sudo apt-get install ia32-libs

