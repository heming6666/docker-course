#  Docker Ignore
为了防止敏感文件或目录被错误地包含在镜像中，你可以添加一个名为.dockerignore的文件。

## 例子
Dockerfile将工作目录复制到Docker镜像中。因此，这将包括潜在的敏感信息，比如密码文件，我们希望在镜像之外进行管理。用指令cat Dockerfile查看Dockerfile。

```bash
cat Dockerfile
```
构建镜像用：
```bash
docker build -t passwd .
```
查看输出用：
```bash
docker run passwd ls /app
```
这会包含密码文件。
## 忽略文件（Ignore File）

下面的指令会在我们的.dockerignore里面包含password.txt，确保它不会意外地出现在一个容器里。
.dockerignore文件将会被存储在源代码控制中，并与团队分享，以确保每个人都是一直的。
 
 ```bash
echo password.txt >> .dockerignore

```
忽略文件支持目录和正则表达式来定义约束，这的那类似于.gitignore。这个文件还可以用来改进构建次数，我们将在下一步进行研究。

下面构建镜像，因为有Docker Ignore文件，所以不需要包含密码文件。

```bash
docker build -t nopassword .

```
查看输出使用：
```bash
docker run nopassword ls /app

```

## 小贴士
如果你需要将密码作为RUN命令的一部分，那么你需要复制、执行和删除这些文件，作为单个RUN命令的一部分。只有Docker容器的最终状态被持久化到镜像。



