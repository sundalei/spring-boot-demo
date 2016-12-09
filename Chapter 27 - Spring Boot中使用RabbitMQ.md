# Spring Boot中使用RabbitMQ

很久没有写Spring Boot的内容了，正好最近在写Spring Cloud Bus的内容，因为内容会有一些相关性，所以先补一篇关于AMQP的整合。

## Message Broker与AMQP简介

Message Broker是一种消息验证、传输、路由的架构模式，其设计目标主要应用于下面这些场景：

- 消息路由到一个或多个目的地
- 消息转化为其他的表现方式
- 执行消息的聚集、消息的分解，并将结果发送到他们的目的地，然后重新组合相应返回给消息用户
- 调用Web服务来检索数据
- 响应事件或错误
- 使用发布-订阅模式来提供内容或基于主题的消息路由

AMQP是Advanced Message Queuing Protocol的简称，它是一个面向消息中间件的开放式标准应用层协议。AMQP定义了这些特性：

- 消息方向
- 消息队列
- 消息路由（包括：点到点和发布-订阅模式）
- 可靠性
- 安全性

## RabbitMQ

本文要介绍的RabbitMQ就是以AMQP协议实现的一种中间件产品，它可以支持多种操作系统，多种编程语言，几乎可以覆盖所有主流的企业级技术平台。

### 安装

在RabbitMQ官网的下载页面```https://www.rabbitmq.com/download.html```中，我们可以获取到针对各种不同操作系统的安装包和说明文档。这里，我们将对几个常用的平台一一说明。

下面我们采用的Erlang和RabbitMQ Server版本说明：

- Erlang/OTP 19.1
- RabbitMQ Server 3.6.5

### Windows安装

1. 安装Erland，通过官方下载页面```http://www.erlang.org/downloads```获取exe安装包，直接打开并完成安装。
2. 安装RabbitMQ，通过官方下载页面```https://www.rabbitmq.com/download.html```获取exe安装包。
3. 下载完成后，直接运行安装程序。
4. RabbitMQ Server安装完成之后，会自动的注册为服务，并以默认配置启动起来。

![install on windows](./images/5-1.png)
