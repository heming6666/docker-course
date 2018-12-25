# 环境变量
检查单个容器和镜像可以为你提供更多的上下文，在生产中可能有数千个容器的生产环境中，限制对您想要的容器的响应是很有用的。

## 过滤容器
docker ps命令允许你根据标签名和值指定一个过滤器。例如，下面的查询将返回所有带有user标签键的容器，其值为kfcoding。
```bash
docker ps --filter "label=user=scrapbook"
```
## 过滤镜像
同样的过滤方法可以应用于镜像建立时所使用的标签。
```bash
docker images --filter "label=vendor=kfcoding"
```
## 注解
当查询标签键名和值时，是大小写敏感的。这就是为什么遵循一致的模式和推荐的指导方针是很重要的。