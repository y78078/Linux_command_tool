# wifi tool

## wpa_cli
## wpa_supplicant
### wpa_supplicant -i mlan0-c /etc/wpa_supplicant.conf &

     network={
	     ssid="home"
	     scan_ssid=1
	     key_mgmt=WPA-PSK
	     psk="very secret passphrase"
     }
     network={
	     ssid="home1"
	     mode=2
	     key_mgmt=NONE
     }
     
http://bigpxuan.blogspot.tw/2016/12/wpasupplicant.html
