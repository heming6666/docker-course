# Docker镜像
标签镜像的工作方式与容器相同，但当镜像构建时，它们被设置在Dockerfile中。当一个容器启动时，镜像的标签将被应用到容器实例中。

## 单个标签
在Dockerfile中，你可以使用LABEL指令来分配标签。中标签vendor下面是用剪贴簿创建的。
```bash
LABEL vendor=katacoda
```
## 多个标签
如果我们想要分配多个标签，我们可以使用下面的格式，在每一行上使用一个标签，使用反斜杠("\")。注意，我们使用的DNS符号格式与第三方工具相关。
```bash
LABEL vendor=Katacoda \
com.katacoda.version=0.0.5 \
com.katacoda.build-date=2016-07-01T10:47:29Z \
com.katacoda.course=Docker
```