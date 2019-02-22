---
layout: post
title: 「Spring文档阅读」导论
date: 2019-02-01
categories: spring
---



### 前言

这个系列文章主要针对Spring框架做一次结构性的认知，了解Spring在软件开发中所涉及到的功能

[参考文档-https://docs.spring.io/spring/docs/5.1.4.RELEASE/spring-framework-reference](https://docs.spring.io/spring-framework/docs/current/spring-framework-reference)

`备注:文章主要涉及内容主要来源Spring官网和维基百科`

* **什么是Spring**

  **Spring Framework** 是一个开源的Java／Java EE全功能栈的应用程序框架，以Apache License 2.0开源许可协议的形式发布。该框架基于 Expert One-on-One Java EE Design and Development一书中的代码，最初由Rod Johnson和Juergen Hoeller等开发。Spring Framework提供了一个简易的开发方式，这种开发方式，将避免那些可能致使底层代码变得繁杂混乱的大量的属性文件和帮助类。

* **Spirng Framework 5结构图**

  ![spring-overview](/Users/jian/blog/source/assets/img/picture/diagram-boot-reactor.svg)

* **Pivotal公司**

  **Pivotal**是一家位于美国加州的计算机软件公司，由VMware和EMC合资成立，其前身则是Pivotal Labs实验室；Pivotal目前运营并维护着Spring framework

* **Spring framework特性**

    * 核心内容: IOC, AOP，events, resources, i18n, validation, data binding, type conversion, SpEL, .
    * 测试框架: mock objects, TestContext framework, Spring MVC Test, `WebTestClient`.
    * 数据访问: transactions, DAO support, JDBC, ORM, Marshalling XML.
    * web编程：Spring MVC, WebSocket, SockJS, STOMP messaging.
    * web响应式编程：Spring WebFlux, WebClient, WebSocket.
    * Integration: remoting, JMS, JCA, JMX, email, tasks, scheduling, cache.
    * 支持语言: Kotlin, Groovy, dynamic languages.

* **Spring项目列表**

    * `Spring Boot`
    * `Spring Framework`
    * `Spring Data`
    * `Spring Cloud`
    * `Spring Cloud Data Flow`
    * `Spring Security`
    * `Spring Session`
    * `Spring Integration`
    * `Spring HATEOAS`
    * `Spring REST Docs`
    * `Spring Batch`
    * `Spring IO Platform`
    * `Spring AMQP`
    * `Spring for Android`
    * `Spring CredHub`
    * `Spring for Apache Kafka`
    * `Spring LDAP`
    * `Spring Mobile`
    * `Spring Roo`
    * `Spring Shell`
    * `Spring Statemachine`
    * `Spring Test HtmlUnit`
    * `Spring Vault`
    * `Spring Web Flow`
    * `Spring Web Services`

* Spring涉及规范API
    
    * Servlet API（JSR 340）
    * WebSocket API（JSR 356）
    * 并发实用程序（JSR 236）
    * JSON绑定API（JSR 367）
    * Bean验证（JSR 303）
    * JPA（JSR 338）
    * JMS（JSR 914） 
    * 依赖注入（JSR 330）
    * 通用注解（JSR 250）

### 系列文章目标

* Spring核心：依赖注入和面向切面编程
* Spring事务管理机制
* Spring数据访问技术
* Spring Web框架结构
* Spring通用规范集成
* 项目快速起步：Spring Boot
* 资源访问限制：Spring Security
* 分布式基础：Spring Cloud




