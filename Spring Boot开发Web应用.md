# Spring Boot开发Web应用

> [Spring Boot快速入门](/Spring%20Boot快速入门.md)中我们完成了一个简单的RESTful Service，体验了快速开发的特性。
> 在留言中也有朋友提到如何把处理结果渲染到页面上。那么本篇就在上篇基础上介绍一下如何进行Web应用的开发。

# 静态资源访问

在我们开发Web应用的时候，需要引用大量的js、css、图片等静态资源。

## 默认配置

Spring Boot默认提供静态资源目录位置需置于classpath下，目录名需符合如下规则：

* /static
* /public
* /resources
* /META-INF/resources

举例：我们可以在src/main/resources/目录下创建static，在该位置放置一个图片文件。启动程序后，尝试访问http://localhost:8080/D.jpg。如能显示图片，配置成功。


