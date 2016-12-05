# Spring Boot工程结构推荐

> 今天看了一位简书上朋友发来的工程，于是想到应该要写这么一篇。前人总结的最佳实践案例可以帮助我们免去很多不必要的麻烦。花点时间来看一下本文，绝对物超所值。

## 工程结构（最佳实践）

Spring Boot框架本身并没有对工程结构有特别的要求，但是按照最佳实践的工程结构可以帮助我们减少可能会遇见的坑，尤其是Spring包扫描机制的存在，如果您使用最佳实践的工程结构，可以免去不少特殊的配置工作。

### 典型示例

* root package结构：```com.example.myproject```
* 应用主类```Application.java```置于root package下，通常我们会在应用主类中做一些框架配置扫描等配置，我们放在root package下可以帮助程序减少手工配置来加载到我们希望被Spring加载的内容
* 实体（Entity）与数据访问层（Repository）置于```com.example.myproject.domain```包下
* 逻辑层（Service）置于```com.example.myproject.service```包下
* Web层（web）置于```com.example.myproject.web```包下

```
com
  +- example
    +- myproject
      +- Application.java
      |
      +- domain
      |  +- Customer.java
      |  +- CustomerRepository.java
      |
      +- service
      |  +- CustomerService.java
      |
      +- web
      |  +- CustomerController.java
      |
```

**看看您现在的功能是否这样配置，如果不是，不妨尝试改变一下，看看是否可以去掉一些@Configuration配置？**
