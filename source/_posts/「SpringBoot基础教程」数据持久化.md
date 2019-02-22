---
layout: post
title: 「SpringBoot基础教程」数据持久化
date: 2019-02-11
categories: spring
---


>数据持久化，顾名思义就是指将数据持久化到数据库中；所以我们在这一章节中我们会和大家一起讨论数据持久化的一些概念和技术；在以前项目开发中，想到持久化，我们就会思考：用`Mybatis`还是`Hibernate`呢？但是我却不会以这两个持久化框架作为讲解的主要内容，而是`Spring data`


#### 基本概念

* **什么是Spring Data**

Spring Data是为数据访问提供熟悉且一致的基于Spring的编程模型，同时仍保留底层数据存储的特​​殊特性;它使数据访问技术，关系数据库和非关系数据库，map-reduce框架和基于云的数据服务变得简单易用，其实质数据服务的抽象模型;其中我们会主要讨论`Spring Data JPA`和`Spring Data JDBC`两个不同的实现

* **JPA规范**

JPA指java持久化API，主要包括对象/关系映射，java持久化查询语言(JPQL)等

#### Spring Data JDBC集成

>参考书籍「Domain Driven Design」

* 添加maven配置
   
   ```xml
   <dependency>
	  <groupId>org.springframework.boot</groupId>
	  <artifactId>spring-boot-starter-jdbc</artifactId>
   </dependency>
   ```

   ```xml
   <dependency>
	  <groupId>mysql</groupId>
	  <artifactId>mysql-connector-java</artifactId>
	  <version>5.1.21</version>
   </dependency>
   ```

* 配置数据源信息

   ```java
	spring.datasource.url=jdbc:mysql://localhost:3306/test
	spring.datasource.username=dbuser
	spring.datasource.password=dbpass
	spring.datasource.driver-class-name=com.mysql.jdbc.Driver

   ```

* 添加数据库表信息

   ```sql
   SELECT * FROM test.User;CREATE TABLE `User` (
	  `ID` int(11) NOT NULL,
	  `NAME` varchar(45) DEFAULT NULL,
	  `AGE` int(11) DEFAULT NULL,
	  PRIMARY KEY (`ID`)
	) ENGINE=InnoDB DEFAULT CHARSET=utf8;
   ```


#### Spring Data JPA集成


#### Springboot集成hibernate


