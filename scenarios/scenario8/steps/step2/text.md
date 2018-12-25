# 创建链接
要连接到源容器，你可以用选项`--link <container-name|id>:<alias>`。容器名称指的是我们在前面步骤中定义的源容器，而别名定义了主机的昵称。

通过设置别名，我们将应用程序如何配置和基础结构如何配置分开。这意味着当连接到其他环境时，应用程序的配置不用改变。

## Link 的工作原理
在这个例子中，我们提出了一个与我们redis-server容器相连的Alpine容器。我们已经把别名定义为redis。当一个链接被创建时，Docker将做两件事。

首先，Docker将根据与容器的链接设置一些环境变量。这些环境变量为你提供了一种通过已知名称引用端口和IP地址等信息的方法。

你可以输出所有环境变量，使用指令env。例如：
```bash
docker run --link redis-server:redis alpine env
```
其次，Docker将会更新容器的HOSTS文件的主机名称，其中包含三个名称、原始版本、别名和hash=id。你可以使用cat /etc/hosts输出容器主机条目。
```bash
docker run --link redis-server:redis alpine cat /etc/hosts
```
## 例子
有了一个链接，你就可以以同样的方式ping源容器，就像在你的网络中的运行的服务器一样。
```bash
docker run --link redis-server:redis alpine ping -c 1 redis
```


