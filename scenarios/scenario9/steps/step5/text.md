# 断开连接的容器
通过我们的网络创建，我们可以使用CLI来探索细节。

下面的指令将会列出我们主机上的所有网络。

```bash
docker network ls
```

我们可以探索这个网络，看看哪个容器是附加的，以及它们的IP地址。
```bash
docker network inspect frontend-network
```
下面的指令将redis容器与frontend-network断开连接。
```bash
docker network disconnect frontend-network redis
```

## 总结
本节课程解释了如何使用Docker Networks。Docker Networks提供了一种将多个容器连接在一起的方法。通过使用嵌入式DNS服务器，它们可以使用有名的名称和别名相互通信。
