# Spring Boot快速入门
# 简介

在您第1次接触和学习Spring框架的时候，是否因为其繁杂的配置而退却了？在你第n次使用Spring框架的时候，是否觉得一堆反复黏贴的配置有一些厌烦？那么您就不妨来试试使用Spring Boot来让你更易上手，更简单快捷地构建Spring应用！

Spring Boot让我们的Spring应用变的更轻量化。比如：你可以仅仅依靠一个Java类来运行一个Spring引用。你也可以打包你的应用为jar并通过使用java -jar来运行你的Spring Web应用。

Spring Boot的主要优点：

* 为所有Spring开发者更快的入门
* 开箱即用，提供各种默认配置来简化项目配置
* 内嵌式容器简化Web项目
* 没有冗余代码生成和XML配置的要求

# 快速入门
本章主要目标完成Spring Boot基础项目的构建，并且实现一个简单的Http请求处理，通过这个例子对Spring Boot有一个初步的了解，并体验其结构简单、开发快速的特性。
## 系统要求：
* Java 7及以上
* Spring Framework 4.1.5及以上

本文采用**Java 1.8.0_73、Spring Boot 1.3.2**调试通过。
## 使用Maven构建项目

1. 通过**SPRING INITIALIZR**工具产生基础项目
  1. 访问：http://start.spring.io/
  2. 选择构建工具Maven Project、Spring Boot版本1.3.2以及一些工程基本信息，可参考下图所示
  ![Image of SPRING INITIALIZR](http://blog.didispace.com/content/images/2016/02/chapter1-1.png)
  3. 点击Generate Project下载项目压缩包
2. 解压项目包，并用IDE以Maven项目导入，以IntelliJ IDEA 14为例：
  1. 菜单中选择File–>New–>Project from Existing Sources...
  2. 选择解压后的项目文件夹，点击OK
  3. 点击Import project from external model并选择Maven，点击Next到底为止。
  4. 若你的环境有多个版本的JDK，注意到选择Java SDK的时候请选择Java 7以上的版本

## 项目结构解析
![Image of Project Structure](http://blog.didispace.com/content/images/2016/02/chapter1-2.png)
