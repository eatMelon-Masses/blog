---
layout: post
title: 「SpringBoot基础教程」日志框架集成
date: 2019-02-25
categories: spring
---

#### 为什么我们需要日志框架

当我们在本地环境调试时，我们可以通过调试断点的方式去定位bug；但是当程序上到生产环境时，我们就不太可能这样做了，因为这有可能影响正常的业务流程，所以我们更多的会获取日志记录文件，通过检查日志输出去判断问题出现的位置，并在测试环境重现的方式去定位问题

#### 日志框架选型

> 日志框架主要分为两类，日志门面和日志实现；从字面上就知道，日志门面主要是日志API的抽象，而日志实现则是日志具体实现

* 日志门面
  * SLF4j
  * Common-logging
  * Log4j2-api
* 日志实现
  * Log4j
  * LogBack
  * Log4j2
  * java.util.logging



而在SpringBoot项目中，默认是以SLF4j+LLogBack进行日志输出处理的；接下来我会讨论SpringBoot项目内日志输出的配置

* application.properties基本配置项

  <!--可仅仅使用该配置完成日志输出的基本配置-->

  * logging.config = /var/log      <!--定义配置文件位置-->
  * logging.level.*=info       <!--定义日志输出等级-->
  * logging.pattern.console <!--控制台输出样式-->
  * logging.pattern.file <!--文件输出样式-->

  > 更多配置项可根据官方网站进行参考配置

* logback-spring.xml日志配置

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration scan="true" scanPeriod="60 seconds" debug="false">
    <contextName>logback</contextName>

    <!--输出到控制台-->
    <appender name="console" class="ch.qos.logback.core.ConsoleAppender">
        <withJansi>true</withJansi>
        <filter class="ch.qos.logback.classic.filter.ThresholdFilter">
            <level>INFO</level>
        </filter>
        <encoder>
            <pattern>%black(console-) %red(%d{yyyy-MM-dd HH:mm:ss}) %black([%thread]) %highlight(%-5level) %boldMagenta(%logger) - %cyan(%msg%n)</pattern>
            <charset>UTF-8</charset>
        </encoder>
    </appender>

    <!--输出到文件-->
    <appender name="file" class="ch.qos.logback.core.rolling.RollingFileAppender">
        <file>/var/log/logback.llog</file>
        <rollingPolicy class="ch.qos.logback.core.rolling.TimeBasedRollingPolicy">
            <fileNamePattern>logback.%d{yyyy-MM-dd-HH-mm}.log</fileNamePattern>
            <maxHistory>30</maxHistory>
            <totalSizeCap>100M</totalSizeCap>
        </rollingPolicy>
        <encoder>
            <pattern>%d{yyyy-MM-dd HH:mm:ss} [%thread] %-5level %logger{36} - %msg%n</pattern>
            <charset>UTF-8</charset>
        </encoder>
    </appender>

    <root level="DEBUG">
        <appender-ref ref="console" />
        <appender-ref ref="file" />
    </root>
</configuration>
```

**SpringBoot如何统一日志包？**

​           SpringBoot实现日志统一的依据，主要是通过SLF4j+日志适配包实现的

​           **什么是日志适配包？**

​           日志适配包的原理即是将原日志包API做一次替换，以达到日志实现的替换

[如何完成日志适配](https://www.slf4j.org/legacy.html)

#### **日志框架替换**

* 移除默认日志依赖包

  ```xml
  <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter</artifactId>
      <exclusions>
          <exclusion> 
              <groupId>org.springframework.boot</groupId>
              <artifactId>spring-boot-starter-logging</artifactId>
          </exclusion>
      </exclusions>
  </dependency>
  ```

* 添加要引入的日志依赖包

  ```xml
  <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-log4j</artifactId>
  </dependency>
  ```

* 日志配置项配置

  在resource目录下添加log4j.properties文件并配置配置项

