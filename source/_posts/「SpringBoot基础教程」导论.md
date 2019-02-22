---
layout: post
title: 「SpringBoot基础教程」导论
date: 2018-05-11
categories: spring
---


#### 概述

该系列文章主要会针对SpringBoot这个框架进行解读，目的是学习搭建一个通用的应用型框架

#### 开始上手

* 下载springboot初始项目包([下载地址](http://start.spring.io/))
* 添加web配置`spring-boot-starter-web`
* 启动SpringBoot应用进行测试

#### 项目任务

 * [ ] 集成持久化服务
 * [ ] 文档引擎
 * [ ] 数据缓存集成
 * [ ] 异常处理机制
 * [ ] 消息队列集成
 * [ ] 日志框架配置
 * [ ] 配置事务引擎
 * [ ] 后台服务模块整理
 * [ ] 配置数据状态机
 * [ ] 数据权限过滤
 * [ ] 设置模板引擎
 * [ ] 文件处理机制(包括execl,图片等)
 * [ ] 第三方API集成
 * [ ] 创建应用监控环境
 * [ ] 标准化应用发布流程，BUG修复流程，迭代流程

#### 相关术语

 * 版本说明
    
    * BUILD-SNAPSHOT：当前快照
    * M1：里程碑
    * RC1：发布候选人
    * RELEASE：GA发布
    * SR1：服务版本



#### 可参考项目

 * [Guns](https://github.com/stylefeng/Guns)
 * [mall](https://github.com/macrozheng/mall)
 * [tianti](https://github.com/xujeff/tianti)
 * [pig](https://gitee.com/log4j/pig)
 * [smallbun](https://gitee.com/leshalv/smallbun)
 * [non-zero](https://github.com/PGshen/non-zero)

#### Spring学习资料汇总

 * [纯洁的微笑](http://www.ityouknow.com)
 * [扶墙老师说](https://afoo.me)
 * [泥瓦匠](https://www.bysocket.com)
 * [程序猿DD](http://blog.didispace.com)
 * [Spring boot揭秘与实战系列](http://blog.720ui.com/columns/springboot_all)




#### 概述

这个项目主要目的是维护一个简化，可定制的初始模板；目前刚把代码生成器分离到`common-code-generator`内，以及完成最简化代码CRUD和权限管理；同时值得一提的是，这个项目是标准化的前后端分离项目，所以后续对`client`端会做统一通用处理

[项目地址：https://github.com/jianjustin/normal-initialize-project](https://github.com/jianjustin/normal-initialize-project)

#### 项目技术栈

* [X] Spring Boot
* [X] Spring Data
* [X] Spring MVC
* [X] Swagger 2.0
* [X] springfox
* [X] Spring Security
* [ ] redis
* [ ] mybatis
* [ ] ActiveMQ
* [ ] Spring Statemachine
* [ ] Spring Web Flow

#### 项目工作

* [X] 数据库持久化操作--基于Spring Data
* [X] token权限管理
* [X] swagger API管理
* [ ] 标准化OAuth2实现
* [ ] 增加日志输出和标准化生成
* [ ] 文件处理机制(包括execl,图片等)
* [ ] 标准化事务处理机制
* [ ] 添加状态机模型和工作流机制
* [ ] 增加消息队列服务API
* [ ] 单元测试覆盖
* [ ] 应用状态监控 
* [ ] 持久化框架引入MyBatis
* [ ] 引入Spring WebFlux替换Spring MVC
* [ ] 引入Spring Cloud重构项目主体代码
* [ ] 标准化应用发布流程，BUG修复流程，迭代流程

#### 如何联系我

* 邮箱地址：janine.jian.chen@gmail.com
* QQ：717266257


>最后，欢迎大家能够加入其中，体会编码的欢乐












