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

Just follow this: https://github.com/atom/atom

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
Install following dependencies
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

## Pycharm
Trying to run pycharm...
```
OpenJDK Server VM warning: ignoring option MaxPermSize=250m; support was removed in 8.0
[   1653]  ERROR - nse.impl.GeneralLicenseManager - No valid license found
java.lang.Throwable
    at com.intellij.openapi.diagnostic.Logger.error(Logger.java:115)
    at com.intellij.ide.a.g.bb.a(bb.java:107)
    at com.intellij.idea.MainImpl$1.start(MainImpl.java:47)
    at com.intellij.idea.StartupUtil.prepareAndStart(StartupUtil.java:105)
    at com.intellij.idea.MainImpl.start(MainImpl.java:42)
    at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
    at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
    at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
    at java.lang.reflect.Method.invoke(Method.java:483)
    at com.intellij.ide.plugins.PluginManager$2.run(PluginManager.java:91)
    at java.lang.Thread.run(Thread.java:745)
[   1674]  ERROR - nse.impl.GeneralLicenseManager - PyCharm 4.0.4  Build #PY-139.1001
[   1675]  ERROR - nse.impl.GeneralLicenseManager - JDK: 1.8.0_31
[   1676]  ERROR - nse.impl.GeneralLicenseManager - VM: OpenJDK Server VM
[   1676]  ERROR - nse.impl.GeneralLicenseManager - Vendor: Oracle Corporation
[   1677]  ERROR - nse.impl.GeneralLicenseManager - OS: Linux
```
Then to get around this all you have to do is:
```
sudo dnf install java-1.8.0-openjdk
```

Install Ruby
```
sudo yum install -y ruby
```

##Docker

Install docker
```
yum -y install docker-io
systemctl start docker
systemctl enable docker
```
* upgrade:
```
systemctl stop docker
wget https://get.docker.com/builds/Linux/x86_64/docker-latest -O /usr/bin/docker
systemctl start docker
```
Behind a proxy
edit /etc/sysconfig/docker
```
HTTP_PROXY="http://<proxy_host>:<proxy_port>"
HTTPS_PROXY="https://<proxy_host>:<proxy_port>"
http_proxy="${HTTP_PROXY}"
https_proxy="${HTTPS_PROXY}"
```
then run
```
sudo service docker restart
```

##Golang

Set up your GOPATH

If you did not create a GOPATH as part of installation, do so now. The GOPATH is a directory tree where all of your Go code will live. Here are the steps to do that:

Make a directory: mkdir ~/gocode
Tell Go to use that as your GOPATH: export GOPATH=~/gocode
Save your GOPATH so that it will apply to all future shell sessions: echo export GOPATH=$GOPATH >> ~/.bash_profile
Now your Go installation is complete.

Install git and hg
Git and Mercurial are required to allow go get to clone various dependencies.

## Go Fish Shell

cd /etc/yum.repos.d/
wget http://download.opensuse.org/repositories/shells:fish:release:2/Fedora_22/shells:fish:release:2.repo
yum install fish
