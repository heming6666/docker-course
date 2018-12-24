# 查找
已启动的容器运行在后台。使用指令docker ps可以列出所有运行的容器，镜像用来启动容器和正常运行时间。
```bash
docker ps
```
这个命令也会展示friendly name和ID，可以用来查明每个容器的信息。

指令docker inspect` <friendly-name|container-id>`提供更多关于正在运行的容器的信息，比如IP地址。

指令`docker logs <friend-name|container-id>`将展示容器写的信息到标准出错或者标准输出。