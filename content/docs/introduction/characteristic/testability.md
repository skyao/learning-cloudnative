---
date: 2019-01-03T10:00:00+08:00
title: 可测试性(Testability)
menu:
  main:
    parent: "introduction-characteristic"
weight: 129
description : "云原生的特征之可测试性(Testability)"
---



可测试性(Testability)



support Continuous Integration and Continuous Delivery…

The reduction of the vast amount of manual effort witnessed in monolithic applications is not just confined to their deployment as far as CN applications are concerned. From a CN development standpoint, the ability to quickly test and perform quality control on daily software updates is an important aspect. CN applications automate the application development and deployment processes using the paradigms of CI/CD (Continuous Integration and Continuous Delivery).

The goal of CI is that every time source code is added or modified, the build process kicks off & the tests are conducted instantly. This helps catch errors faster and improve quality of the application. Once the CI process is done, the CD process builds the application into an artifact suitable for deployment after combining it with suitable configuration. It then deploys it onto the execution environment with the appropriate identifiers for versioning in a manner that support rollback. CD ensures that the tested artifacts are instantly deployed with acceptance testing.



特色＃4他们支持持续集成和持续交付......

就CN应用程序而言，单片应用程序中大量手动工作的减少不仅限于它们的部署。从CN开发的角度来看，快速测试和执行日常软件更新质量控制的能力是一个重要方面。CN应用程序使用CI / CD（持续集成和持续交付）的范例自动化应用程序开发和部署过程。

CI的目标是每次添加或修改源代码时，构建过程开始，测试立即进行。这有助于更快地捕获错误并提高应用程序的质量。完成CI过程后，CD过程将应用程序与适当的配置组合后，将应用程序构建为适合部署的工件。然后，它以支持回滚的方式将其部署到具有适当版本控制标识符的执行环境中。CD确保通过验收测试立即部署测试的工件。

### 和其他的关系

- 自动化






