# 环境变量
Docker镜像应该被设计成可以从一个环境转换到另一个环境，且不需要进行任何更改或者重新构建。通过遵循这个模式，你可以确信，如果它在一个环境中工作，比如登台，那么它就可以在另一个环境中工作，比如生产。

通过Docker，可以在启动容器时定义环境变量。比如说Node.js，你应该在生产时为_NODEENV定义一个环境变量。

使用-e option，你可以设置名称和变量比如_-e NODEENV=production

## 例子
```bash
docker run -d --name my-production-running-app -e NODE_ENV=production -p 3000:3000 my-nodejs-app
```

## 总结
本课程探讨了如何构建一个用于部署Node.js应用程序的Dockerfile。