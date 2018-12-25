#  数据卷（Data Volumes）
在本节课程中，你将学习如何在容器内使用Docker Volumes来持久数据。Docker Volumes允许在容器和容器版本之间共享目录。

Docker Volumes允许你升级容器、重启机器和共享数据，而不会造成数据丢失。在更新数据库或应用程序版本时，这是必不可少的。

当容器启动时，Docker Volumes被创建和分配。数据卷允许你讲主机目录映射到容器里，以便共享数据。

这种映射是双向的。它允许存储在主机上的数据从容器中访问。它还意味着容器内进程保存的数据保存在主机上。

## 任务
这个例子将使用Redis作为保存数据的一种方式。在下面启动一个Redis容器，并用-v参数创建一个数据卷。这表明，保存在容器内的任何数据到/data目录中应该保存在目录/docker/redis-data的主机上。
```bash
docker run -v /docker/redis-data:/data \
    --name r1 -d redis \
    redis-server --appendonly yes

```
我们可以使用下面的指令将数据传输到Redis实例中。

```bash
cat data | docker exec -I r1 redis-cli --pipe

```
Redis将把这些数据保存到磁盘。在主机上，我们可以研究直接映射，它应该包含Redis数据文件

```bash
ls /docker/redis-data

```
这个目录可以安装到第二个容器。一种用途是让Docker容器在数据上执行备份操作。
```bash
docker run -v /docker/redis-data:/backup ubuntu ls /backup
```