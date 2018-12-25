# 检查
标签和元数据只有在以后可以查看/查询它们。查看待定容器或镜像的所有标签的第一种方法是使用：
```bash
docker inspect
```
## 任务
原网站的环境已经创建了一个名为rd的容器和一个名为katacoda-label-example的镜像。查询它们的标签以了解关于它们的附加信息。
```bash
docker inspect rd
```
使用选项-f，你可以将JSON响应过滤到我们感兴趣的标签部分。
```bash
docker inspect -f "{{json .Config.Label }}" rd
```
## 镜像
检查镜像以相同的方式工作，但是JSON格式略有不同，命名为ContainerConfig而不是Config。
```bash
docker inspect -f "}}json .ContainerConfig.Labels }}" katacoda-label-example
```
即使镜像没有被标记，这些标签也会保留。当一个镜像没有被标记时，它就会有一个名字`<none>`。