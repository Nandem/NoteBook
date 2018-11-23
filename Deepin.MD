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
