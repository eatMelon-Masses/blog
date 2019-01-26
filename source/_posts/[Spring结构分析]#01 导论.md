---
layout: post
title: [Spring结构分析]#01导论
date: 2018-04-22
categories: spring-notes
---



### 前言

这个系列文章主要针对Spring框架做一次结构性的认知，了解Spring在软件开发中所涉及到的功能

`#备注:文章主要涉及内容主要来源Spring官网和维基百科`

* **什么是Spring**

  **Spring Framework** 是一个开源的Java／Java EE全功能栈的应用程序框架，以Apache License 2.0开源许可协议的形式发布。该框架基于 Expert One-on-One Java EE Design and Development一书中的代码，最初由Rod Johnson和Juergen Hoeller等开发。Spring Framework提供了一个简易的开发方式，这种开发方式，将避免那些可能致使底层代码变得繁杂混乱的大量的属性文件和帮助类。

* **Pivotal公司**

  **Pivotal**是一家位于美国加州的计算机软件公司，由VMware和EMC合资成立，其前身则是Pivotal Labs实验室；Pivotal目前运营并维护着Spring framework

* **Spring framework特性**
  * 核心内容: IOC, AOP，events, resources, i18n, validation, data binding, type conversion, SpEL, .
  * 测试框架: mock objects, TestContext framework, Spring MVC Test, `WebTestClient`.
  * 数据访问: transactions, DAO support, JDBC, ORM, Marshalling XML.
  * web框架：Spring MVC and Spring WebFlux.
  * Integration: remoting, JMS, JCA, JMX, email, tasks, scheduling, cache.
  * 支持语言: Kotlin, Groovy, dynamic languages.

* **Spirng Core组成模块**

  * spring-aop
  * spring-beans
  * spring-context
  * spring-core
  * spring-expression

  ![spring-overview](/Users/jian/blog/source/assets/img/picture/spring-overview.png)

[图片来源地址-https://docs.spring.io/spring/docs/4.2.x/spring-framework-reference/html/overview.html](https://docs.spring.io/spring/docs/4.2.x/spring-framework-reference/html/overview.html)

### 系列文章目标

