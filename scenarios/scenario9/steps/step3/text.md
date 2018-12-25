# 连接两个容器

Docker支持多个网络和容器同时被附加到多个网络上。

例如，让我们用一个Node.js应用程序创建一个单独的网络，与我们现有的Redis实例进行通信。

## 任务
第一个任务是用同样的方法创建一个网络
```bash
docker network create frontend-network
```

当使用指令connect时，它可以连接到已有的容器到网络。
```bash
docker network connect frontend-network redis
```

当我们启动web服务器时，由于它连接到同一个网络，它将能够与我们的Redis实例通信。


```bash
docker run -d -p 3000:3000 --net=frontend-network katacoda/redis-node-docker-example

```
