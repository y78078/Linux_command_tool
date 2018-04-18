# network
/sbin/route add –net 0.0.0.0 gw 192.168.31.1 eth0 (Note: setting routing table)
## duplex half/full 10/100
### ethtool
ethtool -s eth1 autoneg off speed 100 duplex full
route add default gw X.X.X.X netmask 255.255.255.0

## wvdial
### pppd
pppd /dev/ttyUSB0 115200 lock nodetach noauth debug
