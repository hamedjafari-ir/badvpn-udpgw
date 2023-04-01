
1- 
sudo apt update -y && apt upgrade -y <br> 

2- 
apt install screen <br>

3- 
apt install lsof <br>

4- 
sudo wget -O /usr/bin/badvpn-udpgw "https://github.com/hamedjafari-ir/badvpn-udpgw/raw/main/badvpn-udpgw64"      <br>

5-
sudo chmod +x /usr/bin/badvpn-udpgw <br>

6-
sudo touch /etc/rc.local <br>

7-
sudo nano /etc/rc.local  <br>
============================================================= <br>

#!/bin/sh -e  
screen -AmdS badvpn badvpn-udpgw --listen-addr 127.0.0.1:7555
exit 0
============================================================= <br> <br> <br>
8-
chmod +x /etc/rc.local <br> <br>

9-
reboot <br>

10-
sudo lsof -i -P -n | grep LISTEN <br>
