#  	创建容器
数据容器是唯一负责存储/管理数据的容器。

像其他容器一样，它们由主机系统管理。然而，当你执行docker ps命令时，它们不会运行。

为了创建一个数据容器，我们首先创建一个有名的容器，以备将来参考。我们使用了busybox作为基础，因为它是小而轻的，假使我们想要探索和移动容器到另一个主机。

在创建容器时，我们还提供了一个选项-v来定义其他容器将在将在何处读取/保存数据。

## 任务

创建一个数据容器来存储构建文件，使用指令：


```bash
docker create -v /config –name dataContainer busybox

```
