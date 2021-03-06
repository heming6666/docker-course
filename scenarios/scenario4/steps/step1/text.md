#  基本镜像
正如我们前面的课程所描述的，所有的镜像都以一个基本镜像开始，最好是尽可能接近你想要的配置。Node.js有预先构建的镜像，每个发行版本都有对应的标签。

Node 7.0的镜像是Node:7-alpine，这是基于Alpine构建的，它比官方镜像更小、更流畅。

除了基本镜像之外，我们还需要创建基本目录，用来记录应用程序从哪里运行的。通过使用`RUN <command>`，我们可以执行命令，就好像它们是从command shell中运行的一样，通过使用mkdir，我们可以创建应用程序将要执行的目录。在这种情况下，理想的目录是/src/app，因为环境用户对这个目录有读/写访问权。

我们可以使用`WORKDIR <directory>`来定义工作目录，以确保所有将来的命令都是从与我们的应用程序相关的目录执行的。

## 任务：定义基本环境
在不同的行中设置`FROM <image>:<tag>` , `RUN <command>` , `WORKDIR <directory>`，
以配置用于部署应用程序的基本环境。