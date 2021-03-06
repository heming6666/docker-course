# 访问单个Redis数据库实例
Redis数据库的运行让Jane很开心，但是让她惊讶的是她不能访问该数据库，这是因为每个容器是沙盒机制运行的。如果一个服务需要通过一个没有在容器中运行的进程来访问，那么端口需要通过主机公开。

一旦端口公开了，就可以访问这个进程，就好像它是在主机操作系统上运行一样。

Jane知道，在默认情况下，Redis数据库在6379端口上运行。他了解到，默认情况下，其他应用程序和库期望一个Redis数据库实例在端口上监听。

## 任务
在阅读了文档之后，Jane发现当容器使用指令`-p <host-port>:<container-port>`时，端口是被绑定的。Jane还发现了在启动容器时定义名称是很有用的。这意味着她不需要使用Bash管道，或者在试图访问日志时继续查找名称。

Jane找到了解决其在后台运行Redis问题的最佳方法，在6379端口上有一个名为redisHostPort使用的下面的指令：
```bash
docker run -d --name redisHostPort -p 6379:6379 redis:latest
```

## 小贴士
默认情况下，主机上的端口映射到0.0.0.0，这意味着所有IP地址。你可以定义端口映射时指定一个特定的IP地址，例如，`-p 127.0.0.1:6379:6379`
