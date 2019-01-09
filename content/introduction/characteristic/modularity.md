---
date: 2019-01-03T10:00:00+08:00
title: 模块化(Modularity)
menu:
  main:
    parent: "introduction-characteristic"
weight: 121
description : "云原生的特征之模块化(Modularity)"
---



模块化(Modularity)



每个应用程序可以进一步细分为称为微服务的服务。这些服务相互协作，尽管最终客户看来他们正在访问单个应用程序。



**The Application is composed of multiple services**: what looks like a single application to the end user, for example a Software-as-a-Service (SaaS) human resources application, or a streaming music service, is actually delivered by a set of co-operating services. Clients interact with the application as a whole; typically via a single API. However, internally the application is made up of multiple cooperating services, much like an object-oriented application is made up of multiple cooperating objects.

**应用程序由多个服务组成**：对最终用户来说，单个应用程序，例如软件即服务（SaaS）人力资源应用程序或流媒体音乐服务，实际上由一组co提供 - 运营服务。客户端作为一个整体与应用程序交互; 通常通过单个API。但是，在内部，应用程序由多个协作服务组成，就像面向对象的应用程序由多个协作对象组成一样。



### Software Architecture based on microservices…

As James Lewis and Martin Fowler define it – “*..the* *microservice* *architectural* *style is an approach to developing a single application as a \**suite of small services**, each **running in its own process** and communicating with lightweight mechanisms, often an HTTP resource API. These services are **built around business capabilities** and **independently deployable** by fully automated deployment machinery. There is a **bare minimum of centralized management** of these services, which may be written in different programming languages and use different data storage technologies*.” [1]

### 基于微服务的特色＃7软件架构......

正如詹姆斯·刘易斯和Martin Fowler的定义是- “ *..the*  *微服务* *架构* *风格是开发一个单一的应用程序作为一种方法  \**套件的小服务**，每一个  **在它自己的进程中运行**  ，并与轻巧的机制，通常是HTTP资源API通信。这些服务  **围绕业务功能构建**  ，  **可**  通过全自动部署机制**独立部署**。有一个  **集中管理的最低限度的**  这些服务，可以用不同的编程语言和使用不同的数据存储技术*。” [1]

微服务是面向服务的体系结构（SOA）体系结构的自然演进。应用程序被分解为松散耦合的业务功能并映射到微服务。每个微服务都是为特定的粒度业务功能而构建的，可以由独立的开发人员或团队来处理。因此，它是一个单独的代码工件，因此不仅从通信角度（通常使用RESTful API与使用JSON / XML表示传递的数据进行通信），而且从构建，部署，升级和维护过程中松散耦合透视。每个微服务可以选择具有其本地化的数据存储。采用这种方法的一个重要优点是，每个微服务都可以使用与应用程序其他部分分开的技术堆栈来创建。Docker容器是运行这些微服务的正确选择。微服务具有一系列优势，包括更容易构建，独立部署和扩展。

Microservices are a natural evolution of the Service Oriented Architecture (SOA) architecture. The application is decomposed into loosely coupled business functions and mapped to microservices. Each microservice is built for a specific granular business function and can be worked on by an independent developer or team. As such it is a separate code artifact and is thus loosely coupled not just from a communication standpoint (typically communication using a RESTful API with data being passed around using a JSON/XML representation) but also from a build, deployment, upgrade and maintenance process perspective. Each microservice can optionally have its localized datastore. An important advantage of adopting this approach is that each microservice can be created using a separate technology stack from the other parts of the application. Docker containers are the right choice to run these microservices on. Microservices confer a range of advantages ranging from easier build, independent deployment and scaling.



设计为松散耦合的微服务：属于同一应用程序的服务通过应用程序运行时相互发现。它们独立于其他服务而存在。当正确集成时，弹性基础架构和应用程序架构可以通过高效和高性能进行扩展。

使用最佳语言和框架开发：云原生应用程序的每项服务都是使用最适合该功能的语言和框架开发的。云原生应用程序是多语言的; 服务使用各种语言，运行时和框架。例如，开发人员可以构建基于在Node.js中开发的WebSockets的实时流服务，同时选择Python和Flask来公开API。开发微服务的细粒度方法使他们能够为特定工作选择最佳语言和框架。

松散耦合的服务允许开发人员独立于另一个服务处理每个服务。通过这种分离，开发人员可以专注于每项服务的核心功能，以提供细粒度的功能。这种方法可以实现整个应用程序的有效生命周期管理，因为每个服务都是独立维护的，并且拥有明确的所有权



以API为中心进行交互和协作：云原生服务使用轻量级API，这些API基于代表性状态转移（REST），Google的开源远程过程调用（gRPC）或NATS等协议。REST被用作通过超文本传输协议（HTTP）公开API的最低公分母。为了提高性能，gRPC通常用于服务之间的内部通信。NATS具有发布 - 订阅功能，可在应用程序内实现异步通信。



### 分层设计

多层应用程序和平台

许多云应用程序采用多层设计，其中存在多个服务层或层。 这些层将后端数据库，中间件和应用程序以及前端处理分开。这种分层设计可根据需要提供更高级别的安全性，应用程序升级模块化以及各个层的独立可扩展性。分层应用程序还可以从云中的共享平台或PaaS应用程序（例如数据库服务）中受益，多个应用程序可以共享这些应用程序以降低维护，许可和运营成本。

Multitiered applications and platforms

Many cloud applications employ a multitiered design wherein there are multiple layers, or tiers, of services. These tiers separate the backend data- base, middleware and applications, and frontend processing. This tiered design facilitates higher levels of security, application upgrade modularity, and independent scalability of individual tiers as needed, based on utilization. Tiered applications also benefit from shared platform or PaaS applications in the cloud, such as a database service, that multiple applications can share for lower cost of maintenance, licensing, and operations.





## ## 和其他特征的关联

### 可扩展性

通过使用微服务，云原生应用程序可以独立自动扩展服务。这在大多数情况下会自动发生，因此不需要每天管理它们。

**Composability**

可组合性 - 每种服务的设计都可以被其他应用程序使用。这通常通过具有明确定义的行为的API来完成。

### 经济性

