# 持久化数据
Jane一直在使用Redis数据库作为一个后台进程，Jane想知道容器如何使用前台进程，比如ps或bash。

在此之前，Jane使用-d来执行一个独立的后台状态的容器。如果没有-d，容器将在前台运行。如果Jane想要与容器交互（例如，要访问bash shell），她可以包含选项 -it。

除了定义容器是在后台或前台中运行，某些镜像允许你重写用于启动镜像的指令。替换默认的指令可以让一个单一的镜像能以多种方式重新使用。例如，Ubuntu镜像可以运行OS命令，也可以使用/bin/bash运行交互式bash提示符。

## 例子
指令：
```bash
docker run ubuntu ps
```
启动了一个Ubuntu容器，并且执行了指令ps，用来显示所有运行在这个容器的进程。

指令：
```bash
docker run -it ubuntu bash
```
允许Jane访问容器里的bash shell。

## 总结
在本节课程，Jane需要运行Redis数据库。Jane决定将其作为一个Docker容器来运行，以使其更易于管理。Jane发现的指令是在开发和生产环境中运行Docker的基础。

在下一节课程，Jane将研究如何构建她自己的Docker镜像。