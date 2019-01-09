---
date: 2019-01-03T10:00:00+08:00
title: 自动化(Automation)
menu:
  main:
    parent: "introduction-characteristic"
weight: 127
description : "云原生的特征之自动化性(Automation)"
---



自动化性(Automation)



The CN application needs to be abstracted completely from the underlying infrastructure stack. This is key as development teams can focus on solely writing their software and does not need to worry about the maintenance of the underlying OS/Storage/Network. One of the key challenges with monolithic platforms (<http://www.vamsitalkstech.com/?p=5617>) is their inability to efficiently leverage the underlying infrastructure as they have a high degree of dependency to it. Further, the lifecycle of infrastructure provisioning, configuration, deployment, and scaling is mostly manual with lots of scripts and pockets of configuration management.

CN应用程序需要从底层基础架构堆栈中完全抽象出来。这是关键，因为开发团队可以专注于单独编写软件，而无需担心底层OS /存储/网络的维护。单片平台（<http://www.vamsitalkstech.com/?p=5617>）面临的主要挑战之一是它们无法有效利用底层基础架构，因为它们对它有很高的依赖性。此外，基础架构配置，配置，部署和扩展的生命周期大多是手动的，具有大量脚本和配置管理口袋。

另一方面，考虑到其规模，CN应用程序必须非常轻松。的*规定部署规模*循环高度与所述应用程序自动调整为满足需求，资源约束和从故障中恢复无缝自动化。我们在之前的博客中讨论了Kubernetes。

The CN application, on the other hand, has to be very light on manual asks given its scale. The *provision-deploy-scale* cycle is highly automated with the application automatically scaling to meet demand and resource constraints and seamlessly recovering from failures. We discussed Kubernetes in one of the previous blogs.



自动化功能：云原生应用程序可以高度自动化。它们与基础设施概念作为代码相得益彰。实际上，仅需要一定程度的自动化来管理这些大型和复杂的应用程序。
