# Spring Boot中使用Swagger2构建强大的RESTful API文档

由于Spring Boot能够快速开发、便捷部署等特性，相信有很大一部分Spring Boot的用户会用来构建RESTful API。
而我们构建RESTful API的目的通常都是由于多终端的原因，这些终端会共用很多底层业务逻辑，因此我们会抽象出这样一层来同时服务于多个移动端或者Web前端。

这样一来，我们的RESTful API就有可能要面对多个开发人员或多个开发团队：IOS开发、Android开发或是Web开发等。
为了减少与其他团队平时开发期间的频繁沟通成本，传统做法我们会创建一份RESTful API文档来记录所有接口细节，然而这样的做法有以下几个问题：

* 由于接口众多，并且细节复杂（需要考虑不同的HTTP请求类型、HTTP头部信息、HTTP请求内容等），
  高质量地创建这份文档本身就是件非常吃力的事，下游的抱怨声不绝于耳。
* 随着时间推移，不断修改接口实现的时候都必须同步修改接口文档，而文档与代码又处于两个不同的媒介，除非有严格的管理机制，不然很容易导致不一致现象。

为了解决上面这样的问题，本文将介绍RESTful API的重磅好伙伴Swagger2，它可以轻松的整合到Spring Boot中，
并与Spring MVC程序配合组织出强大RESTful API文档。它既可以减少我们创建文档的工作量，同时说明内容又整合入实现代码中，
让维护文档和修改代码整合为一体，可以让我们在修改代码逻辑的同时方便的修改文档说明。另外Swagger2也提供了强大的页面测试功能来调试每个RESTful API。
具体效果如下图所示：

![Swagger](/images/swagger2_1.png)

下面来具体介绍，如果在Spring Boot中使用Swagger2。首先，我们需要一个Spring Boot实现的RESTful API工程，若您没有做过这类内容，建议先阅读
[Spring Boot构建一个较为复杂的RESTful APIs和单元测试](https://github.com/sundalei/spring-boot-demo/blob/master/Spring%20Boot%E6%9E%84%E5%BB%BARESTful%20API%E4%B8%8E%E5%8D%95%E5%85%83%E6%B5%8B%E8%AF%95.md)。
