# 在失败时重启
根据你的场景，重新启动一个失败的进程可能会纠正这个问题。Docker可以在停止尝试之前，自动重新尝试启动Docker。


## 例子 
选项-restart=on-failure:#允许你告诉Docker应该再尝试多少次。在下面的例子中，Docker将在停止前重新启动容器三次。

```bash
docker run -d --name restart-3 --restart=on-failure:3 scrapbook/dock-restart-example
```
我们可以从日志中看到，它是在三种情况下启动的。
```bash
docker logs restart-3
```



