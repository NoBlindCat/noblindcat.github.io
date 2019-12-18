# ubuntu系统下关于Docker的login操作

当你搭建了一个私有仓库之后，本地的docker从该仓库上做pull和push可能没什么问题。

但是，当你使用非本地的方法连接，也是就使用类似

    docker pull xxx.xxx.xxx.xxx[ip地址]:xxxx[端口]/[子仓库名]/[镜像名]
    
的命令去拉取或推一些镜像的时候，就会出现

    Error response from daemon: Get http://xxx.xxx.xxx.xxx[ip地址]:xxxx[端口]/[子仓库名]/[镜像名]/manifests/latest: no basic auth credentials
    
这种告诉你别人不认识你不给同的操作。

这个时候就需要Login来完成账号的认证了。

    docker login xxx.xxx.xxx.xxx[ip地址]:xxxx[端口] 
    username: [你的用户名]
    password: [密码]
    
再次执行拉取操作就会发现已经成功了。
