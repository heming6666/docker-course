# 单个主机
Nginx-proxy现在正在监听Docker在开始/停止时提出的事件。已经创建了一个名为kfcoding/doccker-http-server的示例网站，该网站返回它正在运行的机器名。这使我们能够测试我们的代理是否按预期工作。在内部，它是一个PHP和Apache2应用程序，监听端口80。

## 启动容器
对于Nginx-proxy来说，开始将请求发送到一个容器，您需要指定VIRTUAL_HOST环境变量。这个变量定义了请求将来自的领域，并且应该由容器来处理。

在这个场景中，我们将设置主机来匹配我们的DEFAULT_HOST，这样它就可以接受所有的请求。
```bash
docker run -d -p 80 -e VIRTUAL_HOST=proxy.example kfcoding/docker-http-server
```

