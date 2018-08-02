### 查看系统架构
```bash
uname -a #几乎所有 Linux/Unix 系统
dpkg --print-architecture #只适用于基于 Debian 和 Ubuntu 的 Linux 发行版
```

### 启动图形界面以便设置软件源
``` bash
sudo update-manager -c -d
```

### shadowsocks配置
1. 下载github上的[ShadowSocks](https://github.com/shadowsocks/shadowsocks-qt5)，格式为APPImage，右键->properties->permissions->Allow executing file as program，双击即可运行。
2. 设置系统代理为Manual，Socks Host为127.0.0.1:1080（1080为ss中设置的本地端口号）。
3. 重启生效。

### 查看系统架构类型
```bash
uname -a #几乎所有 Linux/Unix 系统适用
dpkg --print-architecture #只适用于基于 Debian 和 Ubuntu 的 Linux 发行版
```

### 中文输入法
1. Ctrl + Alt + T打开终端，输入fcitx检查是否安装fcitx，若没有则根据提示进行安装，否则进行2。
2. 系统设置->Region & Language->Manage Installed Languages->Keyboard input method system->fcitx。
3. （可选）此时重启系统发现已经有默认的中文输入法。但想要安装sougou的话需要去官网下载安装包并双击安装，之后点击小键盘选择搜狗输入法。

### 命令行安装oracle-jdk
``` bash
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java8-installer
```

### 命令行安装IntelliJ IDEA
###### 安装 INTELLIJ IDEA COMMUNITY版本：
``` bash
sudo snap install intellij-idea-community --classic --edge
```
###### 安装INTELLIJ IDEA ULTIMATE版本：
``` bash
sudo snap install intellij-idea-ultimate --classic --edge
```

### 安装Android Studio
下载[Android Studio](https://developer.android.google.cn/studio/)
移动到软件文件夹
```bash
sudo mv android-studio-ide-xxx.xxxxxxx-xxx.zip /opt
```
解压
```bash
sudo unzip android-studio-ide-xxx.xxxxxxx-xxx.zip
```

### 安装CLion
#### 先导工作
```bash
sudo apt-get update
sudo apt-get install g++ ##安装g++编译器
sudo apt-get install make ##make工具
sudo apt-get install cmake ##安装cmake工具

sudo apt-get install bison 
sudo apt-get install libncurses5-dev
sudo apt-get install kdelibs5-dev
```
下载[CLion](https://www.jetbrains.com/clion/download/)。
移动到自己的软件文件夹
```bash
sudo mv Clion-xxxx.x.tar.gz /opt
```
进入软件文件夹并解压
```bash
cd /opt
sudo tar -zxvf CLion-xxxx.x.tar.gz  
```
启动
```bash
cd clion-xxxx.x/bin/  
./clion.sh  
```
选择cmake路径，ok！

### JetBrains系列IDE破解
```bash
sudo vim /etc/hosts
```
加入“0.0.0.0 account.jetbrains.com”
保存（若完了sudo打开导致权限不足又不想sudo重新打开，使用“**:w !sudo tee %**”，注意空格）
百度搜Idea注册码，复制粘贴即可。
