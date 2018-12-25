# 复制文件
有了容器，我们现在可以将本地客户目录的文件复制到容器中。

要将文件复制到一个容器中，你可以使用docker pc命令。下面的命令将复制配置。将文件放到我们的dataContainer的config目录里。


```bash
docker cp config.conf dataContainer:/config/

```
