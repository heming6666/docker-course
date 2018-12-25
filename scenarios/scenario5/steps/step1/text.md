#  OnBuild
在本节课程中，我们将研究如何使用OnBuild指令优化Dockerfile。

虽然Docker是自上而下执行的，但是当镜像被用作另一个镜像的基础时，你可以触发一个指令，以便在以后的时间执行。

这样做的结果是，你可以延迟执行，以依赖于你正在构建的应用程序，例如package.json文件。

下面是Node.js OnBuild Dockerfile。与之前的课程不同，应用程序的命令已经用OnBuild预先修复了。

```bash
FROM node:7
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app
ONBUILD COPY package.json /usr/src/app/
ONBUILD RUN npm install
ONBUILD COPY . /usr/src/app
CMD [ "npm", "start" ]
```
这样做的结果是，我们可以构建这个镜像，但是应用程序特定的命令将不会被执行，直到构建的镜像用作基础镜像为止。然后，它们将作为基础镜像构建的一部分执行。

我们将在接下来的步骤中看到这个基本镜像的样子。


