# 共享Volumes
映射到主机的数据卷对于持久化数据非常有用。但是，为了从另一个容器中获得它们，你需要做的确切的路径，这会使它容易出错。

另一种方法是使用 -volumes-from。参数将映射的卷从源容器映射到正在启动的容器。

在这种情况下，我们将Redis容器的卷映射到一个ubuntu容器。然而，/data目录只存在于我们的Redis容器中，因此从我们的ubuntu容器中可以访问数据。
```bash
docker run --volumes-from r1 -it ubuntu ls /data
```
这使我们能够从其他容器访问卷，而不必关心如何在主机上持久化它们。

