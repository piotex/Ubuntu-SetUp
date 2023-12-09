# Ubuntu-SetUp
...
# Guest Tools
1) Devices > Insert Guest Additions CD image
2) Pop up window > Run
3) CD Icon > open in terminal
```
apt-get update
sudo apt-get install gcc perl make -y
./autorun.sh .
[autorun.sh > (Rightclick) > Run as program]

```

# Copy Paste Error:
```
sudo killall VBoxClient 
sudo VBoxClient-all
```

# Install vs code
```
sudo snap install code --classic
```

# Install pyharm
```
sudo snap install pycharm-community --classic
```

# Install Ansible
```
sudo apt-get install ansible -y
ansible --version
```

# Install Docker
```
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y

sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
docker run hello-world

sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
```
# Install Chrome
```
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb
```
# Install audio
```
sudo apt install ffmpeg -y
sudo add-apt-repository universe
sudo apt install rhythmbox -y
```
# Install video mp4
```
sudo snap install vlc
```
# Install net-tools / ifconfig
```
sudo apt install net-tools -y
```
# Instalacja javy
```
sudo apt install openjdk-11-jre-headless
```
# SSH
```
sudo apt install -y openssh-server
```
# python3 
```
sudo apt install -y python3.10-venv
sudo apt install -y python3-pip
```
# jenkins node ???
https://www.coachdevops.com/2021/06/jenkins-build-agent-setup-how-to-setup.html
# ftp
```
sudo apt update
sudo apt install vsftpd
sudo cp /etc/vsftpd.conf /etc/vsftpd.conf.orig
sudo ufw status
sudo ufw allow 20,21,990/tcp
sudo ufw allow 40000:50000/tcp
sudo ufw status
sudo adduser sammy

sudo mkdir /home/sammy/ftp
sudo chown nobody:nogroup /home/sammy/ftp
sudo chmod a-w /home/sammy/ftp
sudo ls -la /home/sammy/ftp
sudo mkdir /home/sammy/ftp/files
sudo chown sammy:sammy /home/sammy/ftp/files
sudo ls -la /home/sammy/ftp
echo "vsftpd test file" | sudo tee /home/sammy/ftp/files/test.txt

sudo nano /etc/vsftpd.conf

...
write_enable=YES
chroot_local_user=YES
user_sub_token=$USER
local_root=/home/$USER/ftp
pasv_min_port=40000
pasv_max_port=50000
userlist_enable=YES
userlist_file=/etc/vsftpd.userlist
userlist_deny=NO
...

echo "sammy" | sudo tee -a /etc/vsftpd.userlist
cat /etc/vsftpd.userlist
sudo systemctl restart vsftpd
ftp -p 192.168.56.105

sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/vsftpd.pem -out /etc/ssl/private/vsftpd.pem

Country Name (2 letter code) [AU]:au
State or Province Name (full name) [Some-State]:some-state
Locality Name (eg, city) []:city
Organization Name (eg, company) [Internet Widgits Pty Ltd]:company
Organizational Unit Name (eg, section) []:section
Common Name (e.g. server FQDN or YOUR name) []:name
Email Address []:p@gmail.com

sudo nano /etc/vsftpd.conf

#rsa_cert_file=/etc/ssl/certs/ssl-cert-snakeoil.pem
#rsa_private_key_file=/etc/ssl/private/ssl-cert-snakeoil.key
#ssl_enable=NO
rsa_cert_file=/etc/ssl/private/vsftpd.pem
rsa_private_key_file=/etc/ssl/private/vsftpd.pem
ssl_enable=YES
allow_anon_ssl=NO
force_local_data_ssl=YES
force_local_logins_ssl=YES
ssl_tlsv1=YES
ssl_sslv2=NO
ssl_sslv3=NO
require_ssl_reuse=NO
ssl_ciphers=HIGH

sudo systemctl restart vsftpd
```
+ install filezilla client
+ 192.168.56.105 + sammy + 21




























