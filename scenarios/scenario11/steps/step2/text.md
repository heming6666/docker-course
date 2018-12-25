# 系统日志(SysLog)
在默认情况下，Docker日志会输出使用json-file的文件记录器，这以为着存储在主机上的JSON文件中的输出。这可能导致大文件填充磁盘。因此，你可以改变日志驱动程序移动到另一个目的地。

Syslog日志驱动程序将把所有容器日志写到知己的中心Syslog。“sysog是一种广泛使用的消息日志标准。它允许分离生成消息的软件，存储它们的系统，以及报告和分析它们的软件。”（维基百科）

这个日志驱动程序被设计为在syslog被外部系统收集和聚合时使用。

## 例子 
以下的指令会把redis日志重定向到syslog。

```bash
docker run -d --name redis-syslog --log-driver=syslog redis
```
## 访问日志 
如果你试图使用客户端查看日志，你将会收到错误 FATA[0000] "logs" command is supported only for "json-file" logging driver。

相反的，你需要通过syslog流来访问它们。



