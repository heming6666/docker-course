# 运行
有了这个内置的镜像，它可以以一种统一的方式发布到其他的Docker镜像中。当一个容器启动时，它会从主机上的其他进程和网络中被沙盒化。并且你需要给它许可并访问它所需要的内容。

例如，当需要打开并绑定到主机上的网络端口，你需要提供参数`-p <host-port>:<container-port>`。

## 任务
启动我们新构建的镜像，该镜像提供友好的名称和标签。由于它是一个web服务器，所以使用-p参数将端口80绑定到主机。
```bash
docker run -d -p 80:80 webserver-image:v1
```
一旦启动，你就通过指令curl docker访问端口80的结果。
```bash
curl docker
```

