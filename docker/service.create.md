# Docker 创建服务

## 描述

创建一个新的服务

(API 1.24+) 客户端以及守护进程API都必须至少为1.24版本才能使用此命令。在客户端上使用docker version 命令检查客户端和守护进程API的版本号。

(集群) 此命令与群集协调器协同工作。

## 用法

    docker service create [OPTIONS] IMAGE [COMMAND] [ARG...]
    
## 选项(OPTIONS)

| 名字，缩写 | 默认值 | 描述 |
| --------- | ----- | ---- |
| <kbd>--config</kbd> | | (API 1.30+)指定要向服务公开的配置 |
| <kbd>--constraint</kbd> | | 布置约束 |
| <kbd>--container-label</kbd> | | 容器标签 |
| <kbd>--credential-spec</kbd> | | (API 1.29+) 托管服务帐户的凭据规范(仅限Windows) |
| <kbd>--detach , -d</kbd>| | (API 1.29+) 立即退出，不等待服务聚合 |
| <kbd>--dns</kbd> | | (API 1.25+) 设置自定义DNS服务器 |
| <kbd>--dns-option</kbd> | | (API 1.25+) 设置DNS选项 |
| <kbd>--dns-search</kbd> | | (API 1.25+) 设置自定义DNS搜索域 |
| <kbd>--endpoint-mode</kbd> | vip | 端点模式（vip 或 dnsrr） |
| <kbd>--entrypoint</kbd> | | 重写镜像的默认入口点 |
