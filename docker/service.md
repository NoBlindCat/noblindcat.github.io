# Docker 服务

## 描述

管理服务

(API 1.24+) 客户端以及守护进程API都必须至少为1.24版本才能使用此命令。在客户端上使用docker version 命令检查客户端和守护进程API的版本号。

(集群) 此命令与群集协调器协同工作。

## 用法

    docker service COMMAND
    
## 子命令
 
|命令|描述|
|  -----  | ----- |
| docker service create | 创建一个新的服务 |
| docker service inspect | 展示一个或多个服务的详细信息 |
| docker service logs | 获取服务或任务的日志 |
| docker service ls | 列出服务 |
| docker service ps | 列出一个或多个服务的任务状态 |
| docker service rm | 删除一个或多个服务 |
| docker service rollback | 恢复对服务配置的更改 |
| docker service scale | 扩展一个或多个复制的服务 |
| docker service update | 更新一个服务 |

## 父命令

|命令|描述|
|  -----  | ----- |
| docker | Docker CLI的基本命令 |

## 额外描述

管理服务
