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
```kill xxx(pid)
