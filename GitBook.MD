### 创建分支并推送到远程
```bash
git checkout -b xxx
git push origin xxx:xxx
```

### 删除远程分支
```bash
git push origin --delete xxx #常规做法

git push orgin :xxx #简单写法，相当于推送一个空分支到远程分支
```
