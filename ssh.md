# 升級到16.04時，ssh認證會報錯

You can try:

ssh -o KexAlgorithms=diffie-hellman-group14-sha1 -oHostKeyAlgorithms=+ssh-dss my.host.com

Add -v if you want to see what's happening, and -o HostKeyAlgorithms=ssh-dss if it still doesn't work:

ssh -v -o HostKeyAlgorithms=ssh-dss -o KexAlgorithms=diffie-hellman-group14-sha1 my.host.com

You can also, of course, edit /etc/ssh/ssh_config or ~/.ssh/ssh_config, and add:

Host my.host.com *.myinsecure.net 192.168.1.* 192.168.2.*
    HostKeyAlgorithms ssh-dss
    KexAlgorithms diffie-hellman-group1-sha1 
## Exmaple ~/.ssh/config
    Host *
    KexAlgorithms +diffie-hellman-group1-sha1
    HostKeyAlgorithms ssh-dss

