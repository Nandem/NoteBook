# Deepin安装
## 进入系统后一直加载
### 第一次安装临时解决方案
- 开机后进入选择页面，不要enter，按e
- 在倒数第二行添加`nouveau.modeset=0`
- 按F10
### 进入系统后暂时永久性的解决方案
- ctrl + alt + t打开终端界面，输入`sudo gedit /boot/grub/grub.cfg`
- 按ctrl + F找到第一个quiet，在其后输入`nouveau.modeset=0`，保存退出
- 重启查看效果

## dde-dock相关
### dde-dock异常
```bash
# 强行重启dde-dock
sudo killall dde-dock
```

# Deepin安装JDK
## 添加Java-8-Oracle源，复制到终端运行
```
sudo su -
echo "deb http://ppa.launchpad.net/webupd8team/java/ubuntu precise main" | tee -a /etc/apt/sources.list
echo "deb-src http://ppa.launchpad.net/webupd8team/java/ubuntu precise main" | tee -a /etc/apt/sources.list
apt-key adv --keyserver keyserver.ubuntu.com --recv-keys EEA14886
apt-get update
exit
```
## 更新软件列表
```
sudo apt-get update
```
## 执行安装命令
```
sudo apt-get install oracle-java8-installer
```
# 错误处理
## 安装软件或者检查系统升级出现Dependency error
```
sudo apt full-upgrade
```

# 进程管理
## 查看指定端口进程
```netstat -nap | grep xxx(端口号)```

## 结束进程
```kill xxx(pid)```

# 安装Openresty
## [下载最新源码包](https://openresty.org/cn/download.html)
```
wget https://openresty.org/download/openresty-x.xx.x.x.tar.gz
```
## 解压源码包
```
tar -xzvf openresty-x.xx.x.x.tar.gz
```

## 配置
```
# 进入openresty-x.xx.x.x
cd openresty-x.xx.x.x

# 配置
./configure --prefix=/opt/openresty \ # 安装路径
            --with-luajit # 添加lua即时编译
            # 其他配置自行查阅
```

# 安装
```
make
make install
```

# Docker
### 创建docker组
`sudo groupadd docker`
### 将用户添加到docker组里
```
sudo usermod -aG docker $USER  # 这里的$USER是你自己的用户名
awk -F ":" '/docker/{print $4}' /etc/group # 查看是否添加成功
```
### 注销你的账户,以便让你的用户权限生效
### 测试你的用户权限是否生效
```docker -v```

# 文件管理器与vscode快捷键冲突
```xdg-mime default dde-file-manager.desktop inode/directory```

# Vim
|操作|命令|
|:---:|:---:|
|复制整行|yy|
|从光标处粘贴|pp|
|复制内容到系统粘贴板|"+y|
|从系统粘贴板粘贴内容|"+p|
|删除整行|dd|
> 操作系统粘贴板需要查看(输入```:version```命令)当前vim是否支持相应的寄存器，不支持的话需要```sudo apt-get install vim-gnome```

# VirtualBox
## 安装
1. 执行```sudo vim /etc/apt/sources.list```添加源```deb [arch=amd64] https://download.virtualbox.org/virtualbox/debian 发行版代号 contrib```
2. 执行```wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -```和```wget -q https://www.virtualbox.org/download/oracle_vbox.asc -O- | sudo apt-key add -```
3. 执行```sudo apt-get update```
4. 执行```sudo apt-get install virtualbox-x.x```安装相应版本

**后续升级只需执行最后一步即可**
