# 定义设置
Docker Compose支持所有可以使用Docker run的属性。

将两个容器连接在一起，以指定链接属性和列出所需的连接。例如，下面的内容将链接到同一个文件中定义的redis源容器，并将相同的名称分配给别名。
```bash
links:
    - redis
``````
同样的格式也用于其他属性，比如端口
```bash
  ports:
    - "3000"
    - "8000"
```
关于选项的附加文档可以在https://docs.docker.com/compose/compose-file/中找到。

## 任务
更新我们的web容器来公开端口3001并创建一个到Redis容器的链接。