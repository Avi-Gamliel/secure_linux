## update and upgrade
1. apt update 
2. apt dist-upgrade
3. apt install unattended-upgrades
4. dpkg-reconfigure --priority=low unattended-upgrades


## add user
1. adduser -m {USERNAME} -G {GROUP}
  1. -m : create User Home Folder
  2. -G : create in GROUP


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

## install nodejs
1. sudo apt update
2. sudo apt-get install nodejs
3. sudo apt install npm
   

## connect github to linode
1. create ssh-key -> 'ssh-keygen'
2. copy the ssh-key and go github -> 'cat ~/.ssh/id_rsa.pub'
3. In github go to setting
4. in the setting go to SSH
5. add new SSh key
6. in linode connect and create folder
7. in the folder run -> 'git clone <git_ssh_clone_project>'

### cli: 
1. status jail: fail2ban-client status sshd
2. realase from jail: fail2ban-client set {jail} unbanip {IP}  -> fail2ban-client set sshd unbanip 127.0.0.1
3. insert ip to jail: fail2ban-client set {jail}
 banip {IP}

## stop write command history to  .bash_history
unset HISTFILE
