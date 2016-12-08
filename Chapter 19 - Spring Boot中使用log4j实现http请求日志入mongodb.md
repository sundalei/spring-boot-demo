# Spring Boot中使用log4j实现http请求日志入mongodb

之前在[《使用AOP统一处理Web请求日志》](./Chapter%2018%20-%20Spring%20Boot%E4%B8%AD%E4%BD%BF%E7%94%A8AOP%E7%BB%9F%E4%B8%80%E5%A4%84%E7%90%86Web%E8%AF%B7%E6%B1%82%E6%97%A5%E5%BF%97.md)一文中介绍了如何使用AOP统一记录web请求日志。基本思路是通过aop去切web层的controller实现，获取每个http的内容并通过log4j将日志内容写到应用服务器的文件系统中。

但是当我们在集群中部署应用之后，应用请求的日志被分散记录在了不同应用服务器的文件系统上，这样分散的存储并不利于我们对日志内容的检索。解决日志分散问题的方案多种多样，本文思路以在[《使用AOP统一处理Web请求日志》](./Chapter%2018%20-%20Spring%20Boot%E4%B8%AD%E4%BD%BF%E7%94%A8AOP%E7%BB%9F%E4%B8%80%E5%A4%84%E7%90%86Web%E8%AF%B7%E6%B1%82%E6%97%A5%E5%BF%97.md)一文的基础之上，扩展log4j实现将日志写入MongoDB。

## 准备工作

可以先拿[Chapter4-2-4](http://git.oschina.net/didispace/SpringBoot-Learning)工程为基础，进行后续的实验改造。该工程实现了一个简单的REST接口，一个对web层的切面，并在web层切面前后记录http请求的日志内容。

## 通过自定义appender实现

思路：log4j提供的输出器实现自Appender接口，要自定义appender输出到MongoDB，只需要继承AppenderSkeleton类，并实现几个方法即可完成。

### 引入mongodb的驱动

在pom.xml中引入下面依赖

```xml
<dependency>
    <groupId>org.mongodb</groupId>
    <artifactId>mongodb-driver</artifactId>
    <version>3.2.2</version>
</dependency>
```

