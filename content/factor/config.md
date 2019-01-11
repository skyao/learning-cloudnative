---
date: 2019-01-03T10:00:00+08:00
title: 配置
menu:
  main:
    parent: "factor"
weight: 203
description : "云原生12 factor之配置(Config)"
---

Store config in the environment
在环境中存储配置

### 官方介绍

### 在环境中存储配置

通常，应用的 *配置* 在不同 [部署](https://12factor.net/zh_cn/codebase) (预发布、生产环境、开发环境等等)间会有很大差异。这其中包括：

- 数据库，Memcached，以及其他 [后端服务](https://12factor.net/zh_cn/backing-services) 的配置
- 第三方服务的证书，如 Amazon S3、Twitter 等
- 每份部署特有的配置，如域名等

有些应用在代码中使用常量保存配置，这与 12-Factor 所要求的**代码和配置严格分离**显然大相径庭。配置文件在各部署间存在大幅差异，代码却完全一致。

判断一个应用是否正确地将配置排除在代码之外，一个简单的方法是看该应用的基准代码是否可以立刻开源，而不用担心会暴露任何敏感的信息。

需要指出的是，这里定义的“配置”并**不**包括应用的内部配置，比如 Rails 的 `config/routes.rb`，或是使用 [Spring](http://spring.io/) 时 [代码模块间的依赖注入关系](http://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html) 。这类配置在不同部署间不存在差异，所以应该写入代码。

另外一个解决方法是使用配置文件，但不把它们纳入版本控制系统，就像 Rails 的 `config/database.yml` 。这相对于在代码中使用常量已经是长足进步，但仍然有缺点：总是会不小心将配置文件签入了代码库；配置文件的可能会分散在不同的目录，并有着不同的格式，这让找出一个地方来统一管理所有配置变的不太现实。更糟的是，这些格式通常是语言或框架特定的。

**12-Factor推荐将应用的配置存储于 环境变量 中**（ *env vars*, *env* ）。环境变量可以非常方便地在不同的部署间做修改，却不动一行代码；与配置文件不同，不小心把它们签入代码库的概率微乎其微；与一些传统的解决配置问题的机制（比如 Java 的属性配置文件）相比，环境变量与语言和系统无关。

配置管理的另一个方面是分组。有时应用会将配置按照特定部署进行分组（或叫做“环境”），例如Rails中的 `development`,`test`, 和 `production` 环境。这种方法无法轻易扩展：更多部署意味着更多新的环境，例如 `staging`或 `qa` 。 随着项目的不断深入，开发人员可能还会添加他们自己的环境，比如 `joes-staging` ，这将导致各种配置组合的激增，从而给管理部署增加了很多不确定因素。

12-Factor 应用中，环境变量的粒度要足够小，且相对独立。它们永远也不会组合成一个所谓的“环境”，而是独立存在于每个部署之中。当应用程序不断扩展，需要更多种类的部署时，这种配置管理方式能够做到平滑过渡。

### 12-factor apps using Kubernetes

12 Factor App的原则3是“在环境中存储配置”。

这个原则背后的想法是应用程序应完全独立于其配置。换句话说，您应该能够将其移动到另一个环境而无需触摸源代码。

一些开发人员通过创建某种配置文件来实现此目标，指定详细信息，例如目录，主机名和数据库凭据。这是一种改进，但它确实存在某人将配置文件检入源控制存储库的风险。

相反，12个因素应用程序将其配置存储为环境变量; 正如宣言所说，这些“不太可能被意外地检入存储库”，并且它们与操作系统无关。

Kubernetes允许您通过Downward API在清单中指定环境变量，但是由于这些清单本身会在源代码控制中进行检查，这不是一个完整的解决方案。

相反，您可以指定环境变量应该由Kubernetes ConfigMaps或Secrets的内容填充，这些内容可以与应用程序分开。例如，您可以将Pod定义为：

```
apiVersion：v1 
 kind：Pod 
 元数据：
   name：secret-env-pod 
 spec：
   containers：
     -  name：mycontainer 
       image：redis 
 env：        -  name：SECRET_USERNAME           valueFrom：secretKeyRef             ：              name：mysecret               key：username         -  name：SECRET_PASSWORD           valueFrom：secretKeyRef             ：              name：mysecret               key：password         -  name：CONFIG_VERSION           valueFrom：            configMapKeyRef：              name：redis-app-config               key：version.id      

```

如您所见，此Pod接收三个环境变量SECRET_USERNAME，SECRET_PASSWORD和CONFIG_VERSION，前两个来自引用的Kubernetes Secrets，第三个来自Kubernetes ConfigMap。这使您可以使它们远离配置文件。

当然，仍然存在某人错误处理用于创建这些对象的文件的风险，但是它们在一起并制定安全处理策略，而不是清除分散在部署周围的数十个配置文件。

更重要的是，社区中有些人指出，[即使是环境变量也不一定是](https://diogomonica.com/2017/03/27/why-you-shouldnt-use-env-variables-for-secret-data/)出于自身原因的[安全](https://diogomonica.com/2017/03/27/why-you-shouldnt-use-env-variables-for-secret-data/)。例如，如果应用程序崩溃，它可能会将所有环境变量保存到日志中，甚至将它们传输到另一个服务。[DiogoMónica](https://github.com/square/keywhiz)指向一个名为[Keywhiz](https://github.com/square/keywhiz)的工具，您可以将其与Kubernetes一起使用，从而创建安全的秘密存储。



