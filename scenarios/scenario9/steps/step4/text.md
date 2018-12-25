# 	创建别名
在使用docker network时，仍然支持用连接的方式，并提供了一种方法来定义容器的别名。这将为容器提供一个额外的DNS入口名称和被发现的方法。当使用--link嵌入的DNS将保证只在使用--link的容器上进行局部查找结果。

另一种方法是在容器连接到网络时提供别名。

## 用别名连接容器
以下指令将会连接我们的Redis实例到带有db别名的frontend-network。
```bash
docker network create frontend-network2
```
```bash
docker network connect --alias db frontend-network2 redis
```

当容器试图通过名称db访问服务时，它们将被授予我们Redis容器的IP地址。
```bash
docker run --net=frontend-network2 alpine ping -c1 db
```




