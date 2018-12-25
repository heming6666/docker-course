#  Docker日志
当你启动一个容器时，Docker将跟踪这个过程的标准输出和标准错误输出，并通过客户端提供它们。

## 例子
在后台，有一个Redis的实例，它的名字是redis-server。使用客户端时，我们可以使用Docker logs redis-server来访问标准输出和标准错误输出。
```bash
docker logs redis-server
```