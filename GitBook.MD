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
git checkout -b xxx
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
