---
date: 2019-01-03T10:00:00+08:00
title: 可扩展性(Scalability)
weight: 139
description : "云原生的特征之可扩展性(Scalability)"
---



针对现代分布式系统环境进行了优化，能够扩展到数万个自我修复的节点。



应用程序及其所有服务应在需求增加时进行扩展和上下扩展。这种动态管理的服务可确保有效使用资源。

**Each service is elastic**: this means that each service can scale-up or scale-down independently of other services. Ideally the scaling is automatic, based on load or other defined triggers. Cloud computing costs are typically based on usage, and being able to dynamically manage scalability in a granular manner enables efficient use of the underlying resources.

**每项服务都具有弹性**：这意味着每项服务都可以独立于其他服务进行扩展或缩小。理想情况下，基于负载或其他定义的触发器，缩放是自动的。云计算成本通常基于使用，并且能够以细粒度方式动态管理可伸缩性，从而能够有效地使用底层资源。

Scalability: Cloud services enable on-demand capacity and allow organizations to scale up and
out more dynamically. For example, you can cater seasonal demand in a cost-effective way.

可扩展性：云服务支持按需容量，允许组织更加动态地扩展和扩展。 例如，您可以以经济有效的方式满足季节性需求。



*Elasticity*

Applications should be elastic as traffic, demand, and usage increases. Elastic means that an application can scale out (adding more compute resources or additional virtual machines) to handle an increase in workload or utilization. A properly designed cloud-native application should be able to automatically detect high utilization and trigger the necessary steps to start up new VMs or application services to handle peak workloads. Then, when peak utilization diminishes, it should reduce VMs or compute instances.

Legacy applications that were not specifically designed to run in the cloud can often use a VM hypervisor to monitor processor and memory utilization, triggering more VM instances when a manually defined peak- utilization threshold is attained. These elasticity techniques make it possible for the applications to take advantage of the power of the cloud infrastructure to dynamically scale—even if the application wasn’t originally designed as cloud-native; although, a cloud native application is more efficient.

*弹性*

随着流量，需求和使用量的增加，应用程序应具有弹性。弹性意味着应用程序可以向外扩展（添加更多计算资源或其他虚拟机）以处理工作负载或利用率的增加。正确设计的云原生应用程序应该能够自动检测高利用率并触发启动新VM或应用程序服务以处理峰值工作负载的必要步骤。然后，当峰值利用率减少时，它应该减少VM或计算实例。 

未专门设计为在云中运行的传统应用程序通常可以使用VM虚拟机管理程序来监视处理器和内存利用率，在达到手动定义的峰值利用率阈值时触发更多VM实例。这些弹性技术使应用程序可以利用云基础架构的强大功能进行动态扩展 - 即使应用程序最初并非设计为云原生的; 但是，云本机应用程序更有效。

我为什么要迁移到云端？关于BI，分析和云的2016年第四季度TDWI最佳实践报告探讨了这个问题，向组织询问了他们在云中进行分析的三大理由。



这些回应非常具有启发性，并非出乎意料，公司将可扩展性，灵活性和成本列为前三个原因。

![](images/reason-scalability.jpg)



CN架构的首要特征是能够动态支持大量用户，大型开发组织和高度分散的运营团队。当人们认为云计算本质上是多租户时，这一要求就更为重要。

在这个区域内，需要考虑典型的问题 -

1. 能够动态扩展部署足迹（纵向扩展）以及减少占用空间（缩小规模）
2. 能够优雅地处理跨层的故障，从而破坏应用程序的可用性
3. 通过确保组件本身提供松散耦合来适应大型开发团队的能力
4. 能够使用几乎任何类型的基础架构（计算，存储和网络）实施

The first & foremost characteristic of a CN Architecture is the ability to dynamically support massive numbers of users, large development organizations & highly distributed operations teams. This requirement is even more critical when one considers that cloud computing is inherently multi-tenant in nature.

Within this area, the typical concerns need to be accommodated –

1. the ability to grow the deployment footprint dynamically (Scale-up)  as well as to decrease the footprint (Scale-down)
2. the ability to gracefully handle failures across tiers that can disrupt application availability
3. the ability to accommodate large development teams by ensuring that components themselves provide loose coupling
4. the ability to work with virtually any kind of infrastructure (compute, storage and network) implementation



### 和模块化微服务的关系

通过使用微服务，云原生应用程序可以独立自动扩展服务。这在大多数情况下会自动发生，因此不需要每天管理它们。



参考资料

- [从容器到云原生 – 极致弹性](https://yq.aliyun.com/articles/679125)