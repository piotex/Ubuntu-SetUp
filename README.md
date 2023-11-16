# Ubuntu-SetUp
...
# Guest Tools
1) Devices > Insert Guest Additions CD image
2) Pop up window > Run
3) CD Icon > open in terminal
4) apt-get update
5) sudo apt-get install gcc perl make
6) ./autorun.sh .

# Copy Paste Error:
sudo killall VBoxClient <br/>
sudo VBoxClient-all

# Install vs code
sudo snap install code --classic

# Install pyharm
sudo snap install pycharm-community --classic

# Install Ansible
sudo apt-get install ansible -y
ansible --version

# Install Docker

sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \\
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y

sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
docker run hello-world


