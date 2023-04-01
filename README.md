sudo wget -O /usr/bin/badvpn-udpgw "https://github.com/hamedjafari-ir/badvpn-udpgw/raw/main/badvpn-udpgw64"      <br>
sudo touch /etc/rc.local   <br>
sudo nano /etc/rc.local         <br>
`----Import Text-----`
<br>
#!/bin/sh -e   <br>
screen -AmdS badvpn badvpn-udpgw --listen-addr 127.0.0.1:7300  <br>
exit 0   <br>
<br>
`----Import Text-----`

chmod +x /etc/rc.local          <br>           
sudo systemctl status rc-local.service           <br>
sudo chmod +x /usr/bin/badvpn-udpgw             <br>
sudo screen -AmdS badvpn badvpn-udpgw --listen-addr 127.0.0.1:7300        <br>
reboot   <br>
sudo lsof -i -P -n | grep LISTEN        <br>

