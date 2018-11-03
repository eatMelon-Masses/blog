---
layout: post
title: learning-notes-springboot
summary: 记录springboot入门教程以及starters配置使用.
featured-img: aaag
categories: spring-notes
---


## 入门
#### 初始化springboot web项目

* 下载springboot初始项目包([下载地址](http://start.spring.io/))
* 添加web配置`spring-boot-starter-web`
* 添加数据库驱动文件`mysql-connector-java`
* 添加持久层配置`spring-boot-starter-data-jpa`
* 添加api层配置---swagger

#### 基础

  * 集成restful服务
  * wrieMock伪造rest服务
  * 服务异常自定义
  * 日志输出
  * 依赖托管

> 通过spring的platform框架将常用的maven依赖进行集中式管理

  ```
  <parent>
		<groupId>io.spring.platform</groupId>
		<artifactId>platform-bom</artifactId>
		<version>Cairo-SR3</version>
		<relativePath/>
	</parent>
  ```

#### spring security集成

  * maven依赖配置

  ```
  <dependency>
	 <groupId>org.springframework.boot</groupId>
	 <artifactId>spring-boot-starter-security</artifactId>
  </dependency>
  <dependency>
     <groupId>org.springframework.security.oauth</groupId>
	 <artifactId>spring-security-oauth2</artifactId>
  </dependency>
  ```

  * 关闭spring security认证功能

> 在springboot应用内的启动类添加注解

  ```
  @EnableAutoConfiguration(exclude = {
		org.springframework.boot.autoconfigure.security.servlet.SecurityAutoConfiguration.class
  })
  ```
  
  * spring security认证拦截器链

    * UsernamePasswordAuthenticationFilter
	* DefaultLoginPageGeneratingFilter
	* BasicAuthenticationFilter
	* RequestCacheAwareFilter
	* SecurityContextHolderAwareRequestFilter
	* AnonymousAuthenticationFilter
	* SessionManagementFilter
	* ExcaptionTranslationFilter
	* FilterSecurityInterceptor

  * 浏览器基础认证

    通过继承`WebSecurityConfigurerAdapter`进行安全认证配置	

  * 表单认证

  

  * 自定义认证配置
  * 密码加密解密
  * oauth2认证


