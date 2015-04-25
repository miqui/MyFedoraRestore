##Install google chrome
```
cat << EOF > /etc/yum.repos.d/google-chrome.repo
[google-chrome]
name=google-chrome - \$basearch
baseurl=http://dl.google.com/linux/chrome/rpm/stable/\$basearch
enabled=1
gpgcheck=1
gpgkey=https://dl-ssl.google.com/linux/linux_signing_key.pub
EOF

yum install google-chrome-stable
 ```

 ##Install atom.io IDE
```
mkdir -p ~/development/repos
sudo mkdir -p /opt/atom
sudo chown user:user /opt/atom
```
```
sudo yum -y install node npm libgnome-keyring-devel
```
```
sudo -i
curl -sL https://rpm.nodesource.com/setup | bash -
yum remove nodejs npm
yum install nodejs
yum remove gyp
exit
```
```
cd ~/development/repos/
git clone https://github.com/atom/atom
cd atom
./script/build
script/grunt install --install-dir /opt/atom
sudo ln -s /opt/atom/bin/atom /usr/local/bin
```
## Setup go-fish shell
```
#
curl -L https://github.com/bpinto/oh-my-fish/raw/master/tools/install.fish | fish

```
If missing config.sh
```
git clone git://github.com/bpinto/oh-my-fish.git ~/.oh-my-fish
cp ~/.oh-my-fish/templates/config.fish ~/.config/fish/config.fish
```
