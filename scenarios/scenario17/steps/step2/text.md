# 创建多阶段Docker镜像
有了Dockerfile的新语法，构建过程与以前完全相同。

## 任务
使用下面的build命令创建所需的Docker映像。

```bash
docker build -f Dockerfile.multi -t golang-app .
```
结果将会是两个镜像。一个未标记的，用于第一阶段和第二个，更小的镜像，我们的目标镜像。
```bash
docker images
```
如果你收到了错误，`COPY --from=0 /build/out /app/ Unknown flag: from`，这意味着你在运行一个旧版本的Docker，没有多阶段的支持。这个场景的第一步升级了当前的Docker版本。