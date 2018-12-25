# 总是重启
最后，Docker总是可以重启一个失败的容器，在这种情况下，Docker会一直尝试，知道它被明确告知要停止的容器。

## 例子
例如，在崩溃的时候使用always标志自动重启容器。

```bash
docker run -d --name restart-always -restart=always scrapbook/docker-restart-example

```
你可以通过日志指令docker logs restart-always来查看重启。

## 总结
本节课程介绍了如何在崩溃后继续保持容器运行。

