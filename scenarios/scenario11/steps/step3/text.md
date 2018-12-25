# 禁用日志记录
第三种选项是禁用容器上的日志记录。这对于在日志中非常荣昌的容器特别有用。
## 例子
当容器启动时，简单地将log-driver设置为none。没有任何输出将被记录。
```bash
docker run -d --name redis-none --log-driver=none redis
```
## 选择哪个配置？
指令inspect允许你识别特定容器的日志配置。下面的指令将为每个容器输出LogConfig部分。

在步骤1的服务器
```bash
docker inspect --format ‘{{ .HostConfig.LogConfig }}’ redis-server
```

在步骤2中创建的服务器
```bash
docker inspect --format ‘{{ .HostConfig.LogConfig }}’ redis-syslog
```
在这个步骤中创建的服务器
```bash
docker inspect --format ‘{{ .HostConfig.LogConfig }}’ redis-none
```
## 总结
本节课程探讨了如何从容器中访问日志文件，以及如何更改文件的位置。在以后的课程中，我们将探讨如何使用外部日志服务来聚合所有日志。

