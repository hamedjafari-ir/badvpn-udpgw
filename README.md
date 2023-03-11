
sudo touch /etc/rc.local
sudo nano /etc/rc.local

----------------------
#!/bin/sh -e
screen -AmdS badvpn badvpn-udpgw --listen-addr 127.0.0.1:7300
exit 0
----------------------

chmod +x /etc/rc.local
sudo systemctl status rc-local.service
sudo chmod +x /usr/bin/badvpn-udpgw
sudo screen -AmdS badvpn badvpn-udpgw --listen-addr 127.0.0.1:7300
reboot
sudo lsof -i -P -n | grep LISTEN

