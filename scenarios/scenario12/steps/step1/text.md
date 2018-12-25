# 在失败时停止
Docker认为任何带有non-zero代码的容器都崩溃了。默认情况下，崩溃的容器将继续被停止。

## 例子
我们创建了一个特殊的容器，它输出一条消息，然后用代码1退出来模拟崩溃。

你可以使用以下指令启动：
```bash
docker run -d --name restart-default scrapbook/docker-restart-example
```

如果你列出所有容器，包括已经停止的，你将用以下指令看到已经崩溃的容器。
```bash
docker ps -a
```

虽然日志会输出我们的消息，但这现实生活中，它希望指示信息来帮助我们诊断问题。
```bash
docker logs restart-default
```
