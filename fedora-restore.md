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

## VirtualBox
```
su -
## OR ##
sudo -i
```
```
cd /etc/yum.repos.d/

## Fedora 21/20/19/18/17/16/15/14/13/12 users
wget http://download.virtualbox.org/virtualbox/rpm/fedora/virtualbox.repo
```
```
yum update
 ```
 Check you are using latest kernel
 ```
 rpm -qa kernel |sort -V |tail -n 1

uname -r
```
```
reboot
```
Install following depencies
```
## CentOS 7 and RHEL 7 ##
rpm -Uvh http://dl.fedoraproject.org/pub/epel/7/x86_64/e/epel-release-7-5.noarch.rpm
 ```
 ```
 yum install binutils gcc make patch libgomp glibc-headers glibc-devel kernel-headers kernel-devel dkms
 ```
 Finally install vbox
 ```
 yum install VirtualBox-4.3
 ```
 Rebuild kernel modules
 ```
 /etc/init.d/vboxdrv setup
## OR ##
service vboxdrv setup
```
Add vbox user(ie. you) to vbox group
```
usermod -a -G vboxusers user_name
```
Start vbox
```
VirtualBox
```
