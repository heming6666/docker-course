# 定义第二个容器
在前面的步骤中，我们使用当前目录中的Dockerfile作为容器的基础。在这一步中，我们希望使用Docker Hub的现有镜像作为第二个容器。

要找到第二个容器，你只需在新行上使用与以前相同的格式。YAML格式足够灵活，可以在同一个文件中定义多个容器。

## 任务：定义第二个容器
用redis的名字定义第二个容器，它使用的镜像是redis。按照YAML格式，容器的详细信息将是：
```bash
redis:
  image: redis:alpine
  volumes:
    - /var/redis/data:/data
```
    