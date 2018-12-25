# 定义第一个容器
Docker组合基于一个docker-compose.yml文件。该文件定义了启动集群集所需的所有容器和设置。然而，这些属性映射到如何使用docker run指令，现在存储在源代码控制中，并与你的代码共享。

该文件的格式基于YAML（Yet Another Markup Language）。
```bash
container_name:
  property: value
    - or options
```
## 任务：定义第一个容器
在这个场景中，我们有一个node.js应用程序需要连接到Redis。首先，我们需要定义我们的docdocker-compose.yml文件来启动Node.js应用程序。

根据上面的格式，文件需要命名容器'web'，并将构建属性设置为当前目录。我们将在以后的步骤中讨论其他属性。

将下列yaml复制到编辑器中。这将定义一个名为web的容器，它基于当前目录的构建。
```bash
web:
  build: .
```