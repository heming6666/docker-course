#  NGINX代理服务器
在这节课中，我们将探讨如何使用NGINX web服务器在主机上运行的两个容器之间进行负载均衡.

有了Docker，有两种主要的方式可以让容器相互通信。第一个是通过链接，它将容器配置为环境变量和主机条目，允许它们进行通信。第二种方法是使用Service Discovery模式，在这种情况下，第三方提供的信息将会是Docker的API。

Service Discovery模式是应用程序使用第三方系统来识别目标服务的位置的地方。例如，如果我们的应用程序想要与数据库对话，它首先会询问一个API，数据库的IP地址是什么。这个模式允许您快速地重新配置和扩展您的架构，并改进了容错能力，而不是固定的位置。

在这个场景中，我们希望有一个NGINX服务，当装载新容器时，它可以动态地发现和更新它的负载平衡配置。幸运的是，在原网站中这已经被创建了，并且被称为nginx-proxy。

Nginx-proxy接受HTTP请求，并根据请求主机名将请求代理到适当的容器。这对用户来说是透明的，没有任何额外的性能开销

## 属性
在启动代理容器时，需要配置三个键属性。

第一个是用-p 80:80将容器绑定到主机80端口。这确保了所有HTTP请求都是由代理服务器处理的。

第二个是安装docker.sock文件。这是与运行在主机上的Docker守护进程的连接，并允许容器通过API访问它的元数据。Nginx-proxy使用这个来监听事件，然后根据容器IP地址更新NGINX配置。安装文件的工作方式与使用-v/var/run/docker.sock：/tmp/docker.sock:ro。我们指定：ro来限制对只读的访问。

最后，我们可以设置一个可选的`-e DEFAULTHOST=<domain>`。如果一个请求进入并且没有指定任何指定的主机，那么这就是请求将被处理的容器。这使你能够在一台机器上运行多个具有不同域的站点，并返回到一个已知的站点。

## 任务
使用下面的指令来启动nginx-proxy。
```bash
docker run -d -p 80:80 -e DEFAULT_HOST=proxy.example -v /var/run/docker.sock:/tmp/docker.sock:ro --name nginx jwilder/nginx-proxy
```
由于我们使用的是DEFAULT_HOST，任何进来的请求都会被定向到分配给主机proxy.example的容器。