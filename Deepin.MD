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
`docker -v`
