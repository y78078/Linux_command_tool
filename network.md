# network
/sbin/route add –net 0.0.0.0 gw 192.168.31.1 eth0 (Note: setting routing table)
## duplex half/full 10/100
### ethtool
ethtool -s eth1 autoneg off speed 100 duplex full
route add default gw X.X.X.X netmask 255.255.255.0

## wvdial
### pppd
pppd /dev/ttyUSB0 115200 lock nodetach noauth debug

### wvdial.conf

[Dialer Defaults]
Modem = /dev/ttyUSB2
Modem Type = Analog Modem
Baud =115200
ISDN = 0
Init1 = ATZ
Init2 = ATQ0 V1 E1 S0=0 &C1 &D2 +FCLASS=0

;[Dialer thenet]
Phone = *99#
Username = 9180********
Password = 9180********
Stupid Mode = yes
Compuserve = 0
Auto DNS = 1
Dial Command = ATDT
;Baud = 115200
Init3 = AT+CGDCONT=1,"IP","internet"
Init4 = AT+CPIN=0000
