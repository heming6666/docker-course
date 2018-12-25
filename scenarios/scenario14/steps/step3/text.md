# 集群
我们现在已经成功地创建了一个容器来处理我们的HTTP请求。如果我们使用相同的VIRTUAL_HOST启动第二个容器，那么nginx-proxy将在循环负载均衡的场景中配置系统。这意味着第一个请求将被发送到一个容器，第二个请求到第二个容器，然后在一个循环中重复。您可以运行的节点数量是没有限制的。

## 任务
使用与以前相同的命令来启动第二个容器。
```bash
docker run -d -p 80 -e VIRTUAL_HOST=proxy.example kfcoding/docker-http-server
```