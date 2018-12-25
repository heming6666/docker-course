# 部署服务
在默认情况下，Docker使用一个扩展复制模型来决定哪些容器应该在哪个主机上运行。扩展方法确保容器在集群中均匀地部署。这个节点从集群中删除，运行的集装箱分布在可用的其他节点上。

服务的新概念用于跨集群运行容器。这是一个比容器更高级的概念。服务允许您定义如何在规模上部署应用程序。通过更新服务，Docker将以一种管理的方式更新所需的容器。

## 任务
在这种情况下，我们正在部署Docker镜像katacoda/docker-http-server。我们正在定义一个名为http的服务的友好名称，并且它应该附加到新创建的skynet网络中。

为了确保复制和可用性，我们在集群中运行两个实例，即副本。

最后，我们在80端口上把这两个容器放在一起。向集群中的任一节点发送HTTP请求，然后将由集群中的一个容器处理请求。接受该请求的节点可能不是容器响应的节点。相反，Docker在所有可用的容器中进行负载平衡。
```bash
docker service create --name http --network skynet --replicas 2 -p 80:80 katacoda/docker-http-server
```
您可以使用CLI命令docker service ls来查看集群上运行的服务
```bash
docker service ls
```
当容器启动时，您将看到它们使用ps命令。您应该在每个主机上看到一个容器实例。

在第一个主机上列出容器
```bash
docker ps
```
在第二个主机上列出容器
```bash
docker ps
```
如果我们向公共端口发出一个HTTP请求，它将由两个容器运行起来。
```bash
curl docker
···