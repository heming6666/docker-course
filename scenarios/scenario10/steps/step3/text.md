# Read-only Volumes
Mounting Volumes使容器能够完全读取和写入目录。你可以通过添加许可权：ro到mount来指定目录上的只读权限。

如果容器试图修改目录中的数据，那么它将会出错。
```bash
docker run -v /docker/redis-data:/data:ro -it ubuntu rm -rf /data
```


