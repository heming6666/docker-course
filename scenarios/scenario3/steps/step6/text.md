# 构建容器
在写完Dockerfile之后，你需要使用docker build来将其转换为镜像，build命令将包含一个含有Dockerfile的目录，执行步骤并将镜像存储在本地的Docker引擎中，如果因为一个错误而失败，那么构建就会停止。
## 任务
使用指令docker build构建镜像，你可以给镜像取个友好的名称，其指令为`-t <name> option`。

## 总结
你可以使用指令docker images来查看你本地机器上的镜像列表.