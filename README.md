# Ubuntu-SetUp
...
# Guest Tools
1) Devices > Insert Guest Additions CD image
2) Pop up window > Run > 

# Copy Paste Error:
sudo killall VBoxClient <br/>
sudo VBoxClient-all

# Install vs code
"sudo apt install ./<file>.deb"            <br/>
sudo apt-get install wget gpg            <br/>
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg            <br/>
sudo install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg            <br/>
sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'            <br/>
rm -f packages.microsoft.gpg            <br/>

sudo apt install apt-transport-https            <br/>
sudo apt update            <br/>
sudo apt install code # or code-insiders            <br/>
