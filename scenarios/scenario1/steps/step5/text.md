# 持久化数据
在处理了几天的容器之后，Jane意识到存储的数据在删除和重建一个容器时会被删除。但是Jane需要保存数据，并在她重建容器时重用。

容器被设计为无状态。绑定目录（也称为volumes）是使用指令`-v <host-dir>:<container-dir>`来完成。当一个目录被安装时，主机上的目录中存在的文件可以被容器访问，并且任何数据的变更/写入到容器内的目录将被存储在主机上。这允许你在不丢失数据的情况下升级或更改容器。

## 任务
通过为Redis数据库提供Docker Hub文档，Jane已调查了Redis数据库官方镜像存储日志和数据到/data目录中。

任何需要保存在Docker主机上的数据，而不是容器内的数据，都应该存储在`/opt/docker/data/redis`中。

完整解决这个任务的指令是：
```bash
docker run -d --name redisMapped -v /opt/docker/data/redis:/data redis
```
## 小贴士
Docker允许你使用$PWD作为当前目录的占位符。