# 查找
Docker客户端构建命令使用Dockerfile。构建命令执行Dockerfile中的每个指令。其结果是一个构建的Docker镜像，可以启动并运行你的配置应用程序。

构建命令接受一些不同的参数。其格式是`docker build -t <build-directory>`。-t 参数允许你为镜像制定一个友好的名称和一个标记，通常用作版本号。这允许你跟踪构建的镜像，并对正在启用的版本有明确的认识。

## 任务
使用下面的Build命令构建我们的静态HTML镜像。
```bash
docker build -t webserver-image:v1 .
```
你可以使用指令docker images来查看主机上所有镜像的列表。
```bash
docker images
```