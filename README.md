## update and upgrade
1. apt update 
2. apt dist-upgrade
3. apt install unattended-upgrades
4. dpkg-reconfigure --priority=low unattended-upgrades


## add user
1. adduser -m {USERNAME} -G {GROUP}
  1. -m : create User Home Folder
` 2. -G : create in GROUP


## remove login throw ssh root
1. go to /etc/ssh/sshd_config
2. change PremitRootLogin no
3. systemctl restart sshd

## install fail2ban 
1. apt install fail2ban 
2. cd /etc/fail2ban
head -20 jail.conf
3. sudo cp jail.conf jail.local
4. nano jail.local
5. go to service you want and add "enabled = true"
6. sudo systemctl enable fail2ban
7. sudo systemctl start fail2ban
8. sudo systemctl status fail2ban

cli: 
status jail: fail2ban-client status sshd
realase from jail: fail2ban-client set YOURJAILNAMEHERE unbanip 

## stop write command history to  .bash_history
unset HISTFILE
