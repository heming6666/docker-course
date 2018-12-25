# 导出/导入容器
如果我们想要数据容器移动到另一台容器，那么我们可以将它导出到一个.tar文件。

```bash
docker export dataContainer > dataContain.tar
```
指令：
```bash
docker import dataContainer.tar
```
将会导入数据容器回到Docker。
## 总结
本节课程解释了如何使用数据容器。数据容器是管理配置数据的一种很好的方式，可以被其他容器使用。volume-from性能允许我们访问其他容器卷，我们可以利用它来进行调试或备份。



