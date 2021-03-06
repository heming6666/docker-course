#  	创建网络
Docker有两种网络方式。第一个定义了两个容器之间的连接。这个连接更新/etc/hosts和环境变量，以允许容器发现和通信。

另一种方法是创建一个docker网络，容器也可以连接起来。该网络与物理网络具有相似的属性，允许容器比使用连接更自由地访问和移动。

第一个是利用CLI创建一个网络。这个网络允许我们连接多个容器，这个容器将能够互相发现。

在这个例子中，我们将从创建一个后端网络开始。所有连接到我们后端的容器将在这个网络上。

## 任务：创建网络
首先，我们用预定义的名称创建网络。
```bash
docker network create backend-network
```

## 任务：连接到网络
当我们启动新的容器时，我们可以使用-net属性来分配它们应该连接到的网络。

```bash
docker run -d --name=redis --net=backend-network redis

```
在下一步我们将探索所网络中的状态。
