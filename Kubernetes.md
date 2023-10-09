# Kubernetes

生产级别的容器编排系统

## 参考资料

- [Offical Site](https://kubernetes.io/)
- [中文官网](https://kubernetes.io/zh-cn/)
- 



## Introduction

Kubernetes也称为K8s，是用于自动部署、扩缩和管理容器化应用程序的开源系统。

### 基本思路

创建kubernetes集群->



## Key Features

#### [自动化上线和回滚](https://kubernetes.io/zh-cn/docs/concepts/workloads/controllers/deployment/)

Kubernetes 会分步骤地将针对应用或其配置的更改上线，同时监视应用程序运行状况以确保你不会同时终止所有实例。如果出现问题，Kubernetes 会为你回滚所作更改。你应该充分利用不断成长的部署方案生态系统。

#### [服务发现与负载均衡](https://kubernetes.io/zh-cn/docs/concepts/services-networking/service/)

你无需修改应用来使用陌生的服务发现机制。Kubernetes 为每个 Pod 提供了自己的 IP 地址并为一组 Pod 提供一个 DNS 名称，并且可以在它们之间实现负载均衡。

#### [自我修复](https://kubernetes.io/zh-cn/docs/concepts/workloads/controllers/replicaset/#replicationcontroller-如何工作)

重新启动失败的容器，在节点死亡时替换并重新调度容器， 杀死不响应用户定义的健康检查的容器， 并且在它们准备好服务之前不会将它们公布给客户端。

#### [存储编排](https://kubernetes.io/zh-cn/docs/concepts/storage/persistent-volumes/)

自动挂载所选存储系统，包括本地存储、公有云提供商所提供的存储或者诸如 iSCSI 或 NFS 这类网络存储系统。

#### [Secret 和配置管理](https://kubernetes.io/zh-cn/docs/concepts/configuration/secret/)

部署和更新 Secret 和应用程序的配置而不必重新构建容器镜像， 且不必将软件堆栈配置中的秘密信息暴露出来。

#### [自动装箱](https://kubernetes.io/zh-cn/docs/concepts/configuration/manage-resources-containers/)

根据资源需求和其他限制自动放置容器，同时避免影响可用性。 将关键性的和尽力而为性质的工作负载进行混合放置，以提高资源利用率并节省更多资源。

#### [批量执行](https://kubernetes.io/zh-cn/docs/concepts/workloads/controllers/job/)

除了服务之外，Kubernetes 还可以管理你的批处理和 CI 工作负载，在期望时替换掉失效的容器。

#### [IPv4/IPv6 双协议栈](https://kubernetes.io/zh-cn/docs/concepts/services-networking/dual-stack/)

为 Pod 和 Service 分配 IPv4 和 IPv6 地址

#### [水平扩缩](https://kubernetes.io/zh-cn/docs/tasks/run-application/horizontal-pod-autoscale/)

使用一个简单的命令、一个 UI 或基于 CPU 使用情况自动对应用程序进行扩缩。

#### [为扩展性设计](https://kubernetes.io/zh-cn/docs/concepts/extend-kubernetes/)

无需更改上游源码即可扩展你的 Kubernetes 集群。

## 基本认知

### Kubernetes是干什么用的, 具有哪些功能, 使用场景式什么?



### 为什么要用Kubernetes?



### 如何使用?



# 核心概念

## Container

## Pod

Pod是Kubernetes中最小的可部署单元，通常包含一个或多个相关容器，它们共享同一网络命名空间、存储卷和其他资源。

## 服务(Service):

- 将运行在一个或一组 [Pod](https://kubernetes.io/zh-cn/docs/concepts/workloads/pods/) 上的网络应用程序公开为网络服务的方法。

- 服务所针对的 Pod 集（通常）由[选择算符](https://kubernetes.io/zh-cn/docs/concepts/overview/working-with-objects/labels/)确定。 如果有 Pod 被添加或被删除，则与选择算符匹配的 Pod 集合将发生变化。 服务确保可以将网络流量定向到该工作负载的当前 Pod 集合。

    Kubernetes Service 要么使用 IP 网络（IPv4、IPv6 或两者），要么引用位于域名系统 (DNS) 中的外部名称。

    Service 的抽象可以实现其他机制，如 Ingress 和 Gateway。

- *解释*：服务定义了一组Pod的访问规则，使得应用程序可以通过服务名访问这些Pod，而不需要关心它们的具体位置。
- *Go角度*：Go开发者可以使用K8s提供的客户端库来创建、配置和管理服务。

## Namesapce



# 常见问题

## Kubernetes客户端

访问Kubernetes Daemon的终端, kuberctl, API, 其他工具