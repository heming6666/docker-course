# 网络通信
不像使用连接，docker network表现就像传统网络，其中的节点可以被连接/分离。


## 任务：探索
你会注意到的第一件事是Docker不再分配环境变量或更新容器的主机内容。使用以下两个命令进行探索，你会注意到它不再提到其他容器。

```bash
docker run --net=backend-network alpine end
```

```bash
docker run --net=backend-network alpine cat /etc/hosts

```
相反，容器可以通过Docker的嵌入式DNS服务器进行通信。这个DNS服务器通过IP 127.0.0.11分配给所有容器，并在resolv.conf文件中设置。

```bash
docker run --net=backend-network alpine cat /etc/resolv.conf
```

当容器试图通过一个有名的名称，如Redis来访问其他容器时，DNS服务器将返回正确容器的IP地址。在这种情况下，Redis的完全限定名称将是redis.backend-network。
```bash
docker run --net=backend-network alpine ping -c1 redis
```


