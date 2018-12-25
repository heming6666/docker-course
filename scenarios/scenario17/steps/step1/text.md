#  创建Dockerfile
在本节课程中，您将学习如何使用多阶段构建功能来制作更小、更优化的镜像。

该功能是将Golang等语言部署为容器的理想选择。通过拥有多阶段的构建，第一个阶段可以使用更大的Docker镜像作为基础来构建Golang二进制文件。在第二阶段，新构建的二进制文件可以使用更小的基本镜像进行部署。最终的结果是优化Docker镜像。

多阶段特性允许单个Dockerfile包含多个阶段，以便生成所需的、优化的Docker镜像。

在此之前，问题将通过两个Dockerfile解决。一个文件是使用开发容器构建二进制和工件的步骤，第二个文件将对生产进行优化，而不包括开发工具。

通过删除生产镜像中的开发工具，你可以重现攻击面并提高部署时间。

## 示例代码
首先部署一个示例Golang HTTP服务器。目前，采用了两种阶段的Docker构建方法。本节将创建一个新的Dockerfile，它允许使用单个命令构建镜像。
```bash
git clone https://github.com/kfcoding/golang-http-server.git
```

## 多阶段的Dockerfile
使用编辑器，创建一个多阶段的Dockerfile。使用Golang SDK构建二进制文件的第一个阶段。第二阶段将生成的二进制文件复制到一个优化的Docker镜像中。
```bash
# First Stage
FROM golang:1.6-alpine
​
RUN mkdir /app
ADD . /app/
WORKDIR /app
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o main .
​
# Second Stage
FROM alpine
EXPOSE 80
CMD ["/app"]
​
# Copy from first stage
COPY --from=0 /app/main /app
```

