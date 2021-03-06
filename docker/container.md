# 镜像，容器和仓库

## 镜像

容器运行时的只读模板，操作系统+软件运行环境+用户程序。

容器镜像是一个不可变的只读文件，其中包含有关创建Docker容器的说明。每次基于容器镜像文件启动容器时，无论在何处部署容器镜像文件，都将获得完全相同的Docker容器。

例如：一个镜像可以完全包含了Ubuntu操作系统环境，可以把它称作一个Ubuntu镜像。镜像也可以安装了Apache应用程序（或其他软件），可以把它称为一个Apache镜像。

镜像是用来创建容器的。Docker提供了简单的方法来建立新的镜像或者升级现有的镜像，你也可以下载别人已经创建好的镜像。

我们可以大致的把镜像比喻成一个java类：
--------------------
    class User{
                 private String name;
                 private int age;
              }
              
![image.png](./image.png)

如上图所示，镜像采用分层构建机制，最底层为bootfs，其次为rootfs。

- bootfs：用于系统引导的文件系统，包括BootLoader和kernel，容器启动完成后会会被卸载以节约内存资源；

- rootfs：位于bootfs之上，表现为docker容器的根文件系统；

   - 传统模式中，系统启动之时，内核挂载rootfs时会首先将其以“只读”模式挂载，完整性自检完成后将其重新挂载为读写模式；

   - docker中，rootfs由内核以“只读”模式挂载，而后通过“联合挂载”技术额外挂载一个“可写”层，容器中的写操作都在这个层完成。


### 镜像结构

通常，我们下载的镜像可能包含了很多层，位于下层的镜像称为父镜像(parent image)，最底层的称为基础镜像(base image)；最上层为“可读写”层，即可写容器。其下层均为“只读”

如下图所示中，基础镜像为ubuntu，这是可能是一个裁剪过的ubuntu系统，它作为整个镜像的base image；当加入了emacs后，又重新创建了一个包含了ubuntu和emacs的镜像；随后在emacs镜像重新加入Apache，又重新创建了一个包含了ubuntu、emacs、Apache的镜像；接下来，启动容器后，docker会在这些父镜像的最上层附加一层“可写容器”层。

容器在启动时，会将该镜像中的所有父镜像按顺序下载至本地，再启动容器。
![](./imag-layer.png)


## 容器

容器是从镜像创建的应用运行实例，可以将其启动、开始、停止、删除，而这些容器都是相互隔离、互不可见的

可认为docker容器就是独立运行的一个或一组应用，以及它们所运行的必需环境。

我们可以大致理解容器是类实例出的对象：
--------------
     User user = new User()  

## 仓库

Docker仓库（Repository）用来保存镜像,类似与代码仓库，是Docker集中存放镜像文件的场所。

每个服务器上可以有多个仓库。

仓库又分为公有仓库（DockerHub、dockerpool）和私有仓库。

公有的Docker仓库名字是Docker Hub。Docker Hub提供了庞大的镜像集合供使用。这些镜像可以是你自己创建的，或者你也可以在别人的镜像基础上创建。Docker仓库是Docker的 分发 部分。

启动容器时，docker daemon会试图从从本地获取相关镜像；当本地镜像不存在时，其将从Regitry中下载该镜像并保存至本地；pull镜像必须使用https协议，如果要使用http，必须在配置文件中明确指定信任该http站。

![registry.png](./registry.png)

![Repositories, Container and Image](./container-image.png)













## 文章参考
[CSDN:Docker容器之镜像仓库详解](https://blog.csdn.net/ccschan/article/details/88095303)
