#  运行一个容器
Docker称自己是为开发者和系统管理员提供的一个开放平台，利用Docker可以实现应用的搭建、传输和运行。

Docker允许你运行容器。容器是使用沙盒进程运行应用，它依赖于本地操作系统。你的机器可以独立运行多个容器，每个容器里的应用是唯一的。

在这一节课程，你将扮演开发者Jane的角色，你需要为她所开发的应用配置一个新的数据库。经过讨论之后，决定使用较为流行的Redis数据库。

Jane不熟悉Redis数据库要怎么配置，但是她听说使用Docker可以很简单地配置Redis数据库的服务器，将其运用在开发和生产。

这一节课程将讨论她怎么完善她的任务，并且部署Redis数据库当作Docker容器。

Jane通过docker机器可以访问到最新版本的Docker引擎开发环境，她的本地开发机装有Docker客户端，并且可以通过命令行来控制。

第一个任务是找出可以运行Redis数据库的Docker镜像。在Docker里面所有容器的启动都是基于Docker镜像的。这些镜像包含所有需要启动的进程，主机不需要任何的配置和依赖文件。

Jane可以在 https://registry.hub.docker.com/ 里面找到已有的镜像或者是用指令docker search <name>来查询。比如，要找到Redis数据库，你可以使用指令docker search redis来实现。
```bash
docker search redis
```

## 任务
Jane使用了查询指令找到Redis数据库的Docker镜像，它就叫做redis，Jane想要运行最新的版本。因为Redis是一个数据库，所以Jane想要让它运行在后台，以便她可以继续工作。

在后台启动一个容器以完成这次步骤，并在这个容器中运行基于官方镜像的Redis数据库实例。

Docker客户端有一个指令叫做run，使用这个指令可以启动一个基于Docker镜像的容器。它的具体指令是run <options> <image-name>。

Docker默认将运行的程序放在前台。如果需要放在后台执行，则需加上指令-d。例如：
```bash
docker run -d redis
```
Docker默认运行最新可执行版本。如果你需要运行一个特殊版本，你可以在指令后面加上一个标签，例如，3.2版本就是`run -d redis:3.2`。

因为这是Jane第一次使用Redis镜像，它将被下载到本地的Docker机器。


