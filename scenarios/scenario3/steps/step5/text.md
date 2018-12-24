# 默认命令
通过配置Docker镜像并定义了我们想要可访问的端口，现在我们需要定义启动应用程序的命令。

Dockerfile中的CMD行定义了当容器启动时运行的默认命令。如果命令需要参数，那么你需要使用一个数组，例如

```bash
[“cmd”,”-a”,”arga value”,”-b”,”argb-value”]
```
它们将被组合在一起，并将运行命令：
```bash
cmd -a arga value -b argb-value
```

## 任务
运行NGINX的命令是
```bash
nginx -g demon off
```
将此设置为Dockerfile中的默认命令。

## 小贴士
CMD的另一种方法是 ENTRYPOINT，当容器启动时，CMD可以被覆盖，但是入口点定义了一个命令，当容器启动时，它可以将参数传递给它。
在这个例子中，NGNIX将是带有默认命令 -g daemon off的entrypoint。