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
