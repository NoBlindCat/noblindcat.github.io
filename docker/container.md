# Docker

## 镜像

容器运行时的只读模板，操作系统+软件运行环境+用户程序。

例如：一个镜像可以完全包含了Ubuntu操作系统环境，可以把它称作一个Ubuntu镜像。镜像也可以安装了Apache应用程序（或其他软件），可以把它称为一个Apache镜像。

我们可以大致的把镜像比喻成一个java类：
--------------------
    class User{
                 private String name;
                 private int age;
              }

## 容器

容器是从镜像创建的应用运行实例，可以将其启动、开始、停止、删除，而这些容器都是相互隔离、互不可见的

可认为docker容器就是独立运行的一个或一组应用，以及它们所运行的必需环境。

我们可以大致理解容器是类实例出的对象：
--------------
     User user = new User()  

## 仓库

Docker仓库（Repository）用来保存镜像,类似与代码仓库，是Docker集中存放镜像文件的场所

每个服务器上可以有多个仓库。

仓库又分为公有仓库（DockerHub、dockerpool）和私有仓库

![Repositories, Container and Image](./container-image.png)
