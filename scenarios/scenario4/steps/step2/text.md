# 安装NPM
之前，我们配置了基础配置以及我们想要如何部署应用程序。下一个阶段是安装运行应用程序所需的依赖项。对于Node.js来说，是安装NPM。

为了将构建时间保持最短，Docker会缓存中Dockerfile中执行一行的结果，以便在将来的构建中使用。如果有什么变化，那么Docker将会使当前和所有的后效行失效，以确保一切都是最新的。

装完NPM之后，我们只想在package.json发生变化时才重装。如果没有什么变化，我们可以使用缓存版本来加快部署。通过使用`COPY package.json <dest>`，我们可以使命令`RUN npm install`失效，如果package.json文件发生改变。如果文件没有发生改变，那么缓存文件不会被禁用，并且将使用npm安装命令的缓存结果。

## 任务：添加Dockerfile行
以下两行在其他要安装npm的Dockerfile中需要添加。
```bash
COPY package.json /src/app/package.json
​
RUN npm install
```
将它们复制到的Dockerfile中以便它们可以在后面被构建。
### 小贴士
如果你不想使用缓存当作构建的一部分，那么就在docker build里面设置-no-cache=true。