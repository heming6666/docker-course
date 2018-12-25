# 链接到应用程序
通过创建一个链接，应用程序可以以通常的方式连接和与源容器进行通信。

## 应用程序的例子
这里有一个简单的node.js的应用程序，它连接了redis，使用的主机名是redis。
```bash
docker run -d -p 3000:3000 --link redis-server:redis katacoda/redis-node-docker-example
```
