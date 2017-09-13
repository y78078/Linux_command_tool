# establish USB console
OS: Yocto
Board SBC-7112 imx6dl sabresd

## start one time by command 
modprobe g_serial

systemctl start getty@ttyGS0
## stop one time by command 
systemctl stop getty@ttyGS0
## enable every time by command 
systemctl enable getty@ttyGS0
## disable always by command 
systemctl disable getty@ttyGS0

getty wiki: https://wiki.archlinux.org/index.php/Getty

It will show how to set autologin

## enable every time by filesystem
### modprobe part
vi /etc/modules-load.d/g_serial.conf

+++ g_serial

esc --> :wq

### getty part
systemctl enable getty@ttyGS0

pwd = /etc/systemd/system/getty.target.wants/

cp getty@ttyGS0.service getty@ttyGS0.service.backup //(need setting file)

systemctl disable getty@ttyGS0

cp getty@ttyGS0.service.backup getty@ttyGS0.service

ln -s /lib/systemd/system/getty@.service


