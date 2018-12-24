# 查找目录及文件 find/locate
在一个固定端口上运行进程的问题是，你只能运行一个实例。Jane更喜欢运行多个Redis数据库实例，并根据Redis数据库正在运行的端口来配置应用程序。

## 任务
在试验之后，Jane发现仅仅使用指令-p 6379就能使她在一个随机可用的端口上公开Redis数据库。所以她决定测试她的理论，通过以下指令：

```bash
docker run -d --name redisDynamic -p 6379 redis:latest
```

虽然这是可行的，但她现在不知道哪个端口被分配了。幸运的是，可以通过以下指令来查看：

```bash
docker port redisDynamic 6379
```

Jane还发现，docker ps可以列出容器并显示端口映射信息：

```bash
docker ps
```

