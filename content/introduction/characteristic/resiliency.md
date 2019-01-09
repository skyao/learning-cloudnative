---
date: 2019-01-03T10:00:00+08:00
title: 弹性(Resiliency)
menu:
  main:
    parent: "introduction-characteristic"
weight: 126
description : "云原生的特征之弹性(Resiliency)"
---



应对单个容器，机器甚至数据中心的故障，满足不同水平的需求。



如果服务能够在中断和故障中存活并保持在线，则服务具有弹性。此外，他们还可以充分利用云中提供的自动故障转移和灾难恢复机制。

**Each service is resilient**: this means that each service is highly-available and can survive infrastructure failures. This characteristic limits the failure domain, due to software bugs or hardware issues.

**每项服务都具有弹性**：这意味着每项服务都具有高可用性，可以承受基础架构故障。由于软件错误或硬件问题，此特性限制了故障域。





*Resiliency*

Resiliency refers to the application’s ability to survive and remain online during an infrastructure outage or failure. A properly designed cloud-native application would have multiple techniques to retry failed transactions and there would be multiple instances of the application services running on other servers or VMs.

Legacy applications that were not designed for a cloud can use tools within a hypervisor or cloud infrastructure such as traffic load balancing, clustering, and server/VM failover, but these are not as effective and transparent to the end user as a cloud-native application’s resiliency. There are many other aspects of resiliency and cloud-native application design benefits that will be covered later in this chapter.

弹性

弹性是指应用程序在基础设施中断或故障期间生存并保持在线的能力。正确设计的云原生应用程序将具有多种技术来重试失败的事务，并且将在其他服务器或VM上运行多个应用程序服务实例。

不是为云设计的传统应用程序可以使用虚拟机管理程序或云基础架构中的工具，例如流量负载平衡，群集和服务器/ VM故障转移，但这些应用程序对于最终用户而言并不像云原生应用程序那样有效和透明。弹性。弹性和云原生应用程序设计优势还有许多其他方面，本章稍后将对此进行介绍。

 








