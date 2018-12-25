# 优化构建
同样地，我们使用.dockerignore文件来排除敏感文件，我们可以使用它来排除那些我们不想在构建过程中被发送到Docker构建环境的文件。


## 优化
为了加快我们的构建，只需在忽略文件中包含大文件的文件名即可。
```bash
echo big-temp-file.img >> .dockerignore
```
当我们重建镜像时，它会快很多，因为不需要复制100M的文件。
```bash
docker build -t no-large-file-context .
```
当诸如.git之类的大型目录时，这种优化会产生更大的影响。
## 总结
在本节课程中，我们探讨了如何使用.dockerignore来优化构建实践，并确保Docker镜像中不包含敏感文件或文件夹。

