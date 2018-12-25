# Docker Scale
由于Docker Compose了解如何启动应用程序容器，它还可以用来扩展运行的容器数量。

scale选项允许你指定服务，然后指定你想要的实例数量。如果这个数字大于已经运行的实例，那么它将启动额外的容器。如果数量减少，就会停止不需要的容器。

## 任务
使用命令docker-compose scale web=3来扩展你正在运行的web容器的数量。
```bash
docker-compose scale web=3
```
你可以使用docker-compose scale web=1来缩小它的规模。
```bash
docker-compose scale web=1
```