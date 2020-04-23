# 常用命令
|功能|命令|说明|
|:---:|:---|:---:|
|查看日志|```kubectl logs -f <pod_name> -c <container_name>```|```-f```: 类似于tail -f|

# 系统命令
|功能|命令|说明|
|:---:|:---|:---:|
|查看当前上下文|```kubectl config current-context```||
|修改默认命名空间|```kubectl config set-context --current --namespace=<namespace_name>```|```--current```: 设置当前上下文默认命名空间|
