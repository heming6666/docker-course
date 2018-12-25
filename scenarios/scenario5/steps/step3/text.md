# 运行
在前面的步骤以及创建了Dockerfile。构建基于OnBuild的Docker文件的镜像也跟前面一样。OnBuild的指令会像在Dockerfile里面执行的一样。

## 例子：构建&启动
构建的指令：
```bash
docker build -t my-nodejs-app .
```
启动的指令：
```bash
docker run -d --name my-running-app -p 3000:3000 my-nodejs-app
```
## 总结
在这一节中，我们探索了如何使用OnBuild指令来优化Dockerfile，以增加不同应用程序之间的重用，方法是将常用部件转移到基本镜像中。
