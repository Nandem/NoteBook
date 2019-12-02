# 端口 相关
## 端口占用
```
# 找出占用端口pid
sudo lsof -i:port
# 结束进程
sudo kill -9 pid
```

# npm 相关
## 'xxx' not a command
### 对所有账户生效
```
sudo vim /etc/profile
# 文件末尾添加
export PATH="$PATH:/opt/node-vx.x.x-linux-x64/bin"
```
重新登录
### 对当前账户生效
```
sudo vim ~/.bashrc

# 文件末尾添加
PATH=$PATH:/opt/node-vx.x.x-linux-x64/bin
```
重新登录
### 临时生效
```
# 终端直接运行
export PATH=$PATH:/opt/node-vx.x.x-linux-x64/bin
```

# 软件源
## 管理
```
sudo vim /etc/apt/sources.list　　
```
