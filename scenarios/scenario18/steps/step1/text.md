# 例一、名称和镜像作为表
docker ps的格式可以被格式化，只显示与你相关的信息。

## 启动示例容器
用以下指令启动示例容器。
```bash
docker run -d redis
```
## 格式化
标准的docker ps命令输出了name、image used、command、uptime和port information。

要限制显示哪些列，请使用-format__参数。该参数允许使用Go模板语法的预打印容器。
```bash
docker ps --format '{{.Names}} container is using {{.Image}} image'
```
因为是使用GO模板语言的，它包括诸如table之类的辅助函数。
```bash
docker ps --format 'table {{.Names}}\t{{.Image}}'
```