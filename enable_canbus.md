
$ sudo ip link set can0 type can bitrate 250000

$ sudo ip link set up can0

$ candump can0

& cansend can0 5A1#11.22.33.44.55.66.77.88
