# 例二、IP地址列表
然而，格式参数允许支持显示通过docker ps命令已经公开的数据。如果您想要包含更多的信息，比如容器的IP地址，那么数据需要通过docker inspect来获取。

值得庆幸的是，docker检查还支持通过Go模板打印结果。docker ps的容器id可以通过管道输送到docker inspect。

格式化参数可以访问所有容器信息。下面是列出运行容器的所有IP地址的示例。
```bash
docker ps -q | xargs docker inspect --format '{{ .Id }} - {{ .Name }} - {{ .NetworkSettings.IPAddress }}'
```


