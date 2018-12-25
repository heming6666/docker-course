# 生成的NGINX的配置
nginx-proxy会自动为我们创建和配置NGINX，如果您对最终的配置感兴趣，那么您可以使用docker exec输出完整的配置文件，如下所示。
```bash
docker exec nginx cat /etc/nginx/conf.d/default.conf
```
关于何时重新加载配置的附加信息可以在使用docker logs nginx的日志中找到
```bash
docker logs nginx
```
## 总结
在这个场景中，我们介绍了如何使用nginx-proxy来动态地在两个容器之间加载平衡请求。处理每个请求的容器是使用Docker API，当新容器被启动/停止时触发。

这个模式允许我们快速添加额外的节点来服务一个网站，或者使用相同的服务器来运行多个不同的网站。



