# 多个容器
内置的Docker允许您提供多个名称/ids，并在单个窗口中显示它们的stats。

原网站环境现在有三个连接的容器在运行。要查看所有这些容器的统计数据，您可以使用管道和xargs。管道将一个命令的输出传递到另一个命令的输入中，而xargs允许您将该输入作为参数提供给命令。

通过将两者结合起来，我们可以列出docker ps提供的所有运行容器的列表，并将它们作为docker stats的支持。这让我们对整个机器的容器进行了概述。
```bash
docker ps -q | xargs docker stats
```
要退出，使用ctrl+c来停止正在运行的进程。



