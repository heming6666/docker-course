# 检查状态
服务概念允许您检查集群的健康状况和状态以及正在运行的应用程序。

任务
您可以查看与跨集群服务相关联的所有任务的列表。在这种情况下，每个任务都是一个容器
```bash
docker service ps http
```
你可以通过以下指令来查看服务器的详细信息和配置
```bash
docker service inspect --pretty http
```
在每个节点上，您可以询问它当前正在运行什么任务。Self指的是manager节点领导者
```bash
docker node ps self
```
使用节点的ID，您可以查询单个主机
```bash
docker node ps $(docker node ls -q | head -n1)
```
在下一个步骤中，我们将对服务进行扩展，以运行容器的更多实例。