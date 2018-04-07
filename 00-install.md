1. 删除libreoffice
```bash
$ sudo apt-get remove libreoffice
```
2. 删除Amazon的链接
```bash
$ sudo apt-get remove unity-webapps-common
```
3. 删掉基本不用的自带软件
```bash
$ sudo apt-get remove thunderbird totem rhythmbox simple-scan gnome-mahjongg aisleriot gnome-mines cheese transmission-common gnome-orca webbrowser-app gnome-sudoku onboard deja-dup
$ sudo apt-get autoremove
$ sudo apt-get autoclean
```

4. 修改Ubuntu源
```bash
$ sudo cp /etc/apt/sources.list /etc/apt/sources.list_bk
$ sudo gedit /etc/apt/sources.list
$ sudo apt-get update
```
```
# deb cdrom:[Ubuntu 16.04 LTS _Xenial Xerus_ - Release amd64 (20160420.1)]/ xenial main restricted
deb-src http://archive.ubuntu.com/ubuntu xenial main restricted #Added by software-properties
deb http://mirrors.aliyun.com/ubuntu/ xenial main restricted
deb-src http://mirrors.aliyun.com/ubuntu/ xenial main restricted multiverse universe #Added by software-properties
deb http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted multiverse universe #Added by software-properties
deb http://mirrors.aliyun.com/ubuntu/ xenial universe
deb http://mirrors.aliyun.com/ubuntu/ xenial-updates universe
deb http://mirrors.aliyun.com/ubuntu/ xenial multiverse
deb http://mirrors.aliyun.com/ubuntu/ xenial-updates multiverse
deb http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse #Added by software-properties
deb http://archive.canonical.com/ubuntu xenial partner
deb-src http://archive.canonical.com/ubuntu xenial partner
deb http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted multiverse universe #Added by software-properties
deb http://mirrors.aliyun.com/ubuntu/ xenial-security universe
deb http://mirrors.aliyun.com/ubuntu/ xenial-security multiverse
```

5. 安装git和vpnc和curl
```bash
$ sudo apt-get install git vpnc curl
```

6. 安装oh-my-zsh
```bash
$ sudo apt-get install zsh
$ sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

7. 安装Vim
```bash
$ sudo apt-get install vim
```

8. 安装chrome
```bash
$ wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
$ sudo apt-get install libappindicator1 libindicator7
$ sudo dpkg -i google-chrome-stable_current_amd64.deb 
$ sudo apt-get -f install
```

9. 删除Firefox
```bash
$ sudo apt-get purge firefox
```


10. 安装搜狗输入法
```bash
$ echo deb http://archive.ubuntukylin.com:10006/ubuntukylin trusty main | sudo tee /etc/apt/sources.list.d/ubuntukylin.list
$ sudo apt-get update   
$ sudo apt-get install sogoupinyin
$ reboot
```

11. 安装WPS Office
```bash
$ sudo apt-get install wps-office
```


12. 安装openssh-server
```bash
$ sudo apt-get install openssh-server
```

13. 安装桌面美化工具Unity-Tweak
```bash
sudo apt-get install unity-tweak-tool
sudo apt-get install gnome-tweak-tool
```

14. 安装Flatabulous主题
```bash
wget https://github.com/anmoljagetia/Flatabulous/releases/download/16.04.1/Flatabulous-Theme.deb
dpkg -i Flatabulous-Theme.deb
```

15. 安装ultra-flat-icons图标主题
```bash
$ sudo add-apt-repository ppa:noobslab/icons
$ sudo apt-get update
$ sudo apt-get install ultra-flat-icons
$ reboot
```

Albert 
$ sudo add-apt-repository ppa:nilarimogard/webupd8
$ sudo apt-get update
$ sudo apt-get install albert


关闭swap内存交换，桌面版不需要#
vim /etc/sysctl.conf

最后一行加入：
vm.swappiness=0