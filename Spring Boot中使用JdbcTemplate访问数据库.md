# Spring Boot中使用JdbcTemplate访问数据库

之前介绍了很多Web层的例子，包括
[构建RESTful API](/Spring%20Boot%E6%9E%84%E5%BB%BARESTful%20API%E4%B8%8E%E5%8D%95%E5%85%83%E6%B5%8B%E8%AF%95.md)、
[使用Thymeleaf模板引擎渲染Web视图](/Spring%20Boot%E5%BC%80%E5%8F%91Web%E5%BA%94%E7%94%A8.md)，但是这些内容还不足以构建一个动态的应用。
通常我们做App也好，做Web应用也好，都需要内容，而内容通常存储于各种类型的数据库，
服务端在接收到访问请求之后需要访问数据库获取并处理成展现给用户使用的数据形式。
