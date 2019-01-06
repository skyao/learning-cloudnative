---
date: 2019-01-04T18:00:00+08:00
title: 12因素应用
weight: 200
description : "云原生的12因素"
---

## 介绍

12-Factors 经常被翻译为**12因素**，符合12因素的应用则称为**12因素应用**。

### 背景

Heroku（HeroKu于2009年推出公有云PaaS）于2012年提出12因素，告诉开发者如何利用云平台提供的便利来开发更具可靠性和扩展性、更加易于维护的云原生应用。

为此还有一个专门的12因素网站： https://12factor.net/ ，以及这个网站内容的中文版本： https://12factor.net/zh_cn/ 。

援引12因素网站的介绍内容：

> 如今，软件通常会作为服务来交付，被称为web app，或软件即服务（SaaS）。12-Factor 为构建如下的 SaaS 应用提供了方法论：
> 
> - 使用**声明式**格式来搭建自动化，从而使新的开发者花费最少的学习成本加入这个项目
> - 和底层操作系统保持**简洁的契约**，在各个系统中提供**最大的可移植性**
> - 适合在现代的**云平台**上**部署**，避免对服务器和系统管理的额外需求
> - **最小化**开发和生产之间的分歧，实现**持续部署**以实现最大灵活性
> - 可以在工具、架构和开发实践不发生重大变化的前提下实现**扩展**
> 
> 12因素理论适用于以任意语言编写，并使用任意后端服务（数据库、消息队列、缓存等）的应用程序。

援引12因素网站的给出的12因素产生的背景：

> 本文的贡献者参与过数以百计的应用程序的开发和部署，并通过 Heroku 平台间接见证了数十万应用程序的开发，运作以及扩展的过程。
> 
> 本文综合了我们关于 SaaS 应用几乎所有的经验和智慧，是开发此类应用的理想实践标准，并特别关注于应用程序如何保持良性成长，开发者之间如何进行有效的代码协作，以及如何 避免软件污染 。
> 
> 我们的初衷是分享在现代软件开发过程中发现的一些系统性问题，并加深对这些问题的认识。我们提供了讨论这些问题时所需的共享词汇，同时使用相关术语给出一套针对这些问题的广义解决方案。

### 12因素的局限性

12因素创作于2012年左右，SaaS平台非常具有指导意义

12-factor为Web应用程序或SaaS平台的建立非常有用的指导原则，但它在有些地方并不适合微服务体系。

在标准的12个要素以外，还存在哪些因素， 正如Kevin Hoffmann 最近在 O’Reilly 出版的书上提到了超越 12 个因素的应用。

### 内容

12因素具体内容为：

| Factor                                     | 描述                                                         |
| ------------------------------------------ | ------------------------------------------------------------ |
| Codebase<br/>基准代码                      | One codebase tracked in revision control, many deploys<br/>一份基准代码，多份部署 |
| Dependencies<br/>依赖                      | Explicitly declare and isolate dependencies<br/>显式声明依赖关系 |
| Config<br/>配置                            | Store config in the environment<br/>在环境中存储配置         |
| Backing services<br/>后端服务              | Treat backing services as attached resources<br/>把后端服务当作附加资源 |
| Build, release, run<br/>构建，发布，运行   | Strictly separate build and run stages<br/>严格分离构建和运行 |
| Processes<br/>进程                         | Execute the app as one or more stateless processes<br/>以一个或多个无状态进程运行应用 |
| Port binding<br/>端口绑定                  | Export services via port binding<br/>通过端口绑定提供服务    |
| Concurrency<br/>并发                       | Scale out via the process model<br/>通过进程模型进行扩展     |
| Disposability<br/>易处理                   | Maximize robustness with fast startup and graceful shutdown<br/>快速启动和优雅终止可最大化健壮性 |
| Dev/prod parity<br/>开发环境与线上环境等价 | Keep development, staging, and production as similar as possible<br/>尽可能的保持开发，预发布，线上环境相同 |
| Logs<br/>日志                              | Treat logs as event streams<br/>把日志当作事件流             |
| Admin processes<br/>管理进程               | Run admin/management tasks as one-off processes<br/>后台管理任务当作一次性进程运行 |



![](images/cloud-native-12-factor.png)





12因素在云原生架构中的体现：

![](images/diagram-cloud-native-arch-01.svg)





