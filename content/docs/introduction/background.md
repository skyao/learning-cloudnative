---
date: 2019-01-03T10:00:00+08:00
title: 云原生出现的背景
menu:
  main:
    parent: "introduction"
weight: 102
description : "云原生出现的背景"
---

## 软件正在改变世界

Software is Eating The World  ——   by *Mark Andreessen*, in 2011

![](images/SoftwareEatingTheWorld.jpg)

Mark Andreessen是风险投资公司Andreessen-Horowitz的联合创始人和合伙人，该公司投资了Facebook，Groupon，Skype，Twitter，Zynga和Foursquare等，Mark Andreessen也是LinkedIn的投资者。

在2011年8月20日的华尔街日报上，Mark Andreessen发表了名为 "Why Software Is Eating the World" 的文章，当时正值惠普宣布放弃陷入困境的个人电脑业务，转而投入软件投资，并看好未来的增长潜力；与此同时，谷歌计划收购手机制造商摩托罗拉移动公司；苹果在过去几周成为美国最大的公司，以市值来判断，超越埃克森美孚。

援引原文部分内容：


> 我们处于戏剧性和广泛的技术和经济转变的中间，软件公司准备接管大量的经济。
>
> 越来越多的主要企业和行业正运行在软件上并提供在线服务 - 从电影到农业再到国防。许多获奖者都是硅谷式的创业技术公司，他们正在入侵和推翻既有的行业结构。
>
> 为什么现在发生这种情况？
>
> 计算机革命六十年，微处理器发明四十年，现代互联网兴起二十年，通过软件转变行业所需的所有技术终于有效，并可在全球范围内广泛传播。
>
> 十年前，当我在创办的Netscape公司时，大概5000千人使用了宽带互联网，而现在有超过20亿人使用宽带互联网。在接下来的10年里，我预计全球至少有50亿人拥有智能手机，每个人每天都可以随时随地使用这种手机充分利用互联网。
>
> 在后端，软件编程工具和基于互联网的服务可以轻松地在许多行业中推出新的全球软件驱动的初创企业 - 无需投资新的基础设施和培训新员工。2000年，当我的合伙人Ben Horowitz担任第一家云计算公司Loudcloud的首席执行官时，运营基本互联网应用程序每月的成本约为15万美元。今天在亚马逊云中运行相同的应用程序每月花费大约1500美元。

文中列出了被重塑的产业，具体有 : 最大的书店 Amazon、最多人订阅的Video service Netflix、最大的音乐公司iTune、 Spotify and Pandora等、成长最快的娱乐领域 videogame、最好的电影制片厂 Pixar、最大的行销平台 : Google、Groupon、 Facebook等、成长最快的电信公司 : Skype 、成长最快招聘公司 LinkedIn。

文章发表于2011年，在8年后的2019年再来看，感触更加深刻。

>  补充：有兴趣的同学可以看一下这个文章： [A Review of ‘Why Software is Eating The World’: How have the companies fared?](https://www.bigfootcap.com/a-review-of-why-software-is-eating-the-world-how-have-the-companies-fared/): 这是在2018年，有人撰文分析了在上文中提到的几家主要软件公司的发展情况：Facebook/Apple/Amazon/Netflix/Google。

## 移动互联网在加剧变化

在“Software is Eating The World”一文中，作者展望互联网规模时，写道：

> 在接下来的10年里，我预计全球至少有50亿人拥有智能手机，每个人每天都可以随时随地使用手机充分利用互联网。

在8年之后的2019年，我们已经可以清晰的确认Mark Andreessen的预测很正确，移动互联网时代的用户规模已经开始向人口基数看齐。

而移动互联网如此巨大的用户规模会对软件开发有什么影响？

援引Netflix的一页PPT，这里按照规模和变更速度将软件企业划分为四个象限/四种类型：

1. 企业IT：规模小，变化慢，容易处理
2. 电信：规模大，变化慢，主要应对硬件失败
3. 初创公司：规模小，变化快，主要应对软件失败
4. 网络规模的互联网企业：规模大，变化快，软硬件或者说所有东西都会出问题

![](../data/slides2015/images/netflix-development-patterns-for-scale-performance-availability/ppt4.jpg)

在十年前乃至二十年前的互联网时代，大多数软件企业都位于上图左边的两个象限：规模或许有大有小，但是变更速度相对今天都不高。当企业发展壮大时，体现的也更多是在规模上，变更速度并不会发生质的变化。

而今天的移动互联网时代，则都位于上图右边的两个象限：无论规模是大是小，变更速度都要求非常高。并且当企业逐步发展壮大，规模十倍百倍增长时，对变更速度的要求并不会降低，甚至会要求更快。

在移动互联网时代，能够成长并发展起来的这些公司，他们的共同点是什么：

- 快速变更，不断创新，随时调整
- 提供持续可用的服务，因对各种可能的错误和中断
- 弹性可扩展的系统，因对用户规模的快速增长
- 提供新的用户体验，以移动为中心

这样的背景下，对软件开发的有了更高的要求，软件开发的方式也不得不跟随时代而变化：首当其冲的就是如何解决规模越来越大同时变更越来越快的难题。

Pivotal公司的Matt Stine对此描述如下：

> We’re trying to bring a perceived conflict into balance: software-driven business agility vs. software system resiliency. We want to move fast and yet not break things. In order to do this, we're going to change how we build software, not necessarily where we build software. 
>
> 我们正努力平衡感知到的冲突：软件驱动的业务敏捷性 vs. 软件系统的弹性。我们希望快速前行而不破坏事物。为了做到这一点，我们将改变我们构建软件的方式，而不是在哪里构建软件。


## 软件上云大势所趋

将软件迁移到云上是应对这一挑战的自然演化方式，在过去二十年，从物理机到虚拟机到容器，从IaaS诞生到PaaS、CaaS、SaaS、FaaS一路演进，应用的构建和部署变的越来越轻、越来越快，而底层基础设施和平台则越来越强大，以不同形态的云对上层应用提供强力支撑。

关于云的定义，Matt Stine表示：

> Obviously, we need a place to do this: "cloud." I define cloud as any computing environment in which computing, networking, and storage resources can be provisioned and released elastically in an on-demand, self-service manner. 
>
> 显然，我们需要一个地方来做到这一点：“云”。我将云定义为可以按需，自助服务方式弹性配置和发布计算，网络和存储资源的任何计算环境。

2006年AWS通过提供EC2服务开创了IaaS市场。通过按时计费的方式租借服务器，客户不承担资本支出，仅在使用服务时付费。将资本支出（Capex）转变为运营支出（Opex），这是云计算时代的真正开始，而之后PaaS，SaaS等的演进只是超云这个方向一步一步继续前行：

![](images/iaas-paas-saas-comparison.jpg)


## 总结

前面我们谈到了软件对各行各业的渗透和对世界的改变，以及移动互联网时代巨大的用户基数下快速变更和不断创新的需求对软件开发方式带来的巨大推动力，结合上一篇文章描述的过去二十年间云计算的发展演进和软件上云的趋势，我们可以清晰的看到这样一个波澜壮阔的技术浪潮：

- 软件正在改变世界
- 移动互联网让这个变革影响到每一个人
- 传统软件开发方式受到巨大挑战
- 云计算普及，软件上云成为趋势
- 云的形态持续在演进

援引InfoQ主编徐川老师对云计算的总结：

- **云计算的技术逐渐发展成为它本来该有的模样；**
- **以及与这样的云所匹配的软件架构；**
- **以及与这样的架构所匹配的开发流程与方法论。**

云原生由此诞生！

### 参考资料

- [Why Software Is Eating the World](https://a16z.com/2011/08/20/why-software-is-eating-the-world/): by Marc Andreessen
- [Why Software Is Eating The World的读后感](https://www.gss.com.tw/index.php/focus/eis/102-eis67/936-eis67-01)：繁体中文版本
- [A Review of ‘Why Software is Eating The World’: How have the companies fared?](https://www.bigfootcap.com/a-review-of-why-software-is-eating-the-world-how-have-the-companies-fared/): 在2018年，有人撰文分析了在上文中提到的几家主要软件公司的增长情况。
- [Netflix Development Patterns for Scale, Performance & Availability](https://www.slideshare.net/AmazonWebServices/dmg206) ，来自Netflix，2013年
- [2018 年终盘点：我们处在一个什么样的技术浪潮当中？](https://www.infoq.cn/article/H1VZ6dH1DjH5juGO3*pD)：来自InfoQ主编徐川老师



