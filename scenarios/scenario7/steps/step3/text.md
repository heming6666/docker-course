# 挂载Volumes
现在我们的数据容器有了配置，当我们启动需要的配置文件的依赖容器时，我们可以引用容器。

通过使用`—volumes-from <container>`，我们可以从正在启动的容器内的其他容器中使用挂载卷。在这种情况下，我们将启动一个Ubuntu容器，它引用了我们的数据容器。当我们列出配置目录时，它将显示附件容器中的文件。

```bash
docker run --volumes-from dataContainer ubuntu ls /config

```
如果一个/config目录已经存在，那么这个卷将会覆盖并称为所使用的目录。你可以将多个卷映射到一个容器。

