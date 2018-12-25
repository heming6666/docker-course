# 连接到Redis客户端
以同样的方式，你可以连接到源容器和应用程序，你也可以连接到它们自己的客户端工具。
## 启动Redis客户端
下面的命令将会启动一个Redis-cli的实例，并且通过redis的别名连接到它的服务器。
```bash
docker run -it --link redis-server:redis redis redis-cli -h redis
```

## 总结
在本节课程中，我们探讨了Docker如何连接工作，以及如何在两个容器之间进行连接和通信。你可以使用相同的方法将多个容器连接在一起。



