**adguard**
~~~
sudo systemctl disable systemd-resolved
sudo systemctl stop systemd-resolved

edit resolve.conf
sudo nano /etc/resolv.conf

nameserver 1.1.1.1
options edns0 trust-ad
search .
~~~
