---
layout: post
title: 「Spring文档阅读」Spring核心：依赖注入和面向切面编程
date: 2019-02-11
categories: spring
---

这篇文章中，我主要会围绕core模块进行讲解；

#### IOC原理

IOC即控制反转，又被称为依赖注入，其目的是解耦Bean之间的依赖关系；在`org.springframework.beans`和`org.springframework.context`包是Spring框架的IoC容器的基础; `BeanFactory`接口提供了一种能够管理任何类型对象的高级配置机制，而`ApplicationContext`则是`BeanFactory`的超集，目的是添加一系列企业级开发套件

###### Bean配置

* XML配置方式

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"   xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">
	<bean class="org.janine.jian.test.SimpleBean"></bean>
</beans>
```

* 注解配置方式

```java
@Configuration
public class BeanConfig {
	@Bean
    public SimpleBean simpleBean() {
        return new SimpleBean();
    }
}
```

###### 实例化bean容器

```java
ApplicationContext context;
context = new ClassPathXmlApplicationContext("config.xml");
SimpleBean bean = context.getBean(SimpleBean.class);
bean.send();
```

###### ApplicationContext实现

![image-20190205172445335](/Users/jian/blog/source/assets/img/picture/ApplicationContext实现.png)

* ClassPathXmlApplicationContext -- XML配置方式实现bean容器
* FileSystemXmlApplicationContext -- XML配置方式实现bean容器
* AnnotationConfigApplicationContext -- 注解配置方式实现bean容器

###### ApplicationContext接口说明

![image-20190207150036871](/Users/jian/blog/source/assets/img/picture/ApplicationContext接口说明.png)

* EnvironmentCapable : 抽象容器应用模型环境profile和PropertySource
* BeanFactory ：bean容器
* MessageSource  : 进行消息解析和国际化 
* ResourceLoader ： 用于资源加载
* Functionalinterface : 自定义事件监听

####  Bean配置讲解

###### Bean实例化

* 构造函数实例化

  ```xml
  <bean id="exampleBean" class="examples.ExampleBean"/>
  ```

* 静态工厂实例化

  ```xml
  <bean id="clientService" class="examples.ClientService"
  factory-method="createInstance"/>
  ```

###### 依赖注入

* 构造器注入

  ```xml
  <constructor-arg ref="beanId"/>
  ```

* Setter注入

  ```xml
  <property name="beanName" ref="beanId"/>
  ```

> 通过lazy-init="true"将bean实例设置为懒加载

###### Bean生命周期

###### Bean依赖关系

#### ResourceLoader资源加载

Spring内置资源说明：

* `UrlResource`
* `ClassPathResource`
* `FileSystemResource`
* `ServletContextResource`
* `InputStreamResource`
* `ByteArrayResource`