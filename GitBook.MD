### 切换分支
```bash
git checkout xxx　# 切换到xxx分支(如果xxx是文件或者文件夹的话意义大不相同)
```

### 创建分支
```bash
git branch xxx # 创建xxx后并不会切换到该分支
```

### 创建分支并推送到远程
```bash
git checkout -b xxx # 相当于git branch xxx和git checkout xxx的合体
git push origin xxx(本地分支):xxx(远程分支)
```

### 删除分支
```bash
git branch -d xxx
```

### 删除远程分支
```bash
git push origin --delete xxx # 常规做法

git push orgin :xxx # 简单写法，相当于推送一个空分支到远程分支
```

### 重命名分支
```bash
git branch -m oldxxx newxxx
```

### 查看本地分支对应的远程分支
```bash
git branch -vv 
```

# 本地库直接关联远程库并提交
初始化本地项目为git仓库
```bash
git init
```
添加所有需要提交的项目
```bash
git add .
```
初始提交
```bash
git commit -m "xxx"
```
添加远程库
```bash
git add remote origin(不用管别的就写这个) 仓库地址
```
fetch远程库
```bash
git fetch origin
```
pull相关分支
```bash
git pull origin 分支 #需要--allow-unrelated-histories
```
push相关分支
```bash
git push origin
```
> 可能会报错，但一般会直接在命令行进行提示，照着做即可
