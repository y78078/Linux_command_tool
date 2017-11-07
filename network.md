# network

## duplex half/full 10/100
### ethtool
ethtool -s eth1 autoneg off speed 100 duplex full
route add default gw X.X.X.X netmask 255.255.255.0
