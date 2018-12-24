#  创建Dockerfile
Docker镜像从一个基本镜像启动。该基本镜像应该包括应用程序所需的平台依赖项，比如，安装了JVM或CLR。

这个基本镜像被定义为Dockerfile中的指令。Docker镜像是基于Dockerfile的内容构建的。Dockerfile是描述如何部署应用程序的说明列表。

在这个例子中，我们的基本镜像是Nginx的Alpine版本。它在Linux Alpine发行版提供了配置好的web服务器。

## 任务
通过将下面的内容复制到编辑器中，创建你的Dockerfile来构建你的镜像。
```bash
FROM nginx:alpine
COPY . /usr/share/nginx/html
```
第一行定义了我们的基本镜像，第二行将当前目录的内容复制到容器内的特定位置。


