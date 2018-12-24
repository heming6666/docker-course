# 构建和启动容器
要在容器中启动应用程序，首先需要构建一个镜像。
## 例子：构建&启动
构建镜像的指令是：

```bash
docker build -t my-nodejs-app .
```

启动已构建的镜像的指令是：
```bash
docker run -d --name my-running-app -p 3000:3000 my-nodejs-app
```

