# Spring Boot中Web应用的统一异常处理

我们在做Web应用的时候，请求处理过程中发生错误是非常常见的情况。Spring Boot提供了一个默认的映射：```/error```，当处理中抛出异常之后，会转到该请求中处理，并且该请求有一个全局的错误页面用来展示异常内容。

选择一个之前实现过的Web应用（[Chapter3-1-2](http://git.oschina.net/didispace/SpringBoot-Learning/tree/master/Chapter3-1-2)）为基础，启动该应用，访问一个不存在的URL，或是修改处理内容，直接抛出异常，如：

```java
@RequestMapping("/hello")
public String hello() throws Exception {
    throw new Exception("发生错误");
}
```

此时，可以看到类似下面的报错页面，该页面就是Spring Boot提供的默认error映射页面。
