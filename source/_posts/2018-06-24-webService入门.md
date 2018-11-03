---
layout: post
title: webService入门
summary: 了解不同应用间相互调用方式及其特点.
featured-img: aaay
categories: learning-notes
---


## webService概念

定义了应用程序如何在web上实现互操作性,通过暴露API的形式实现服务的查询以及访问

## webService实现方式

### RPC(Remote rocedure call)

>远程过程调用, 很简单的概念, 像调用本地服务(方法)一样调用服务器的服务(方法);通常的实现有`XML-RPC`,`JSON-RPC`
  
### SOAP

>简单对象访问协议（Simple Object Access Protocol）;基于消息进行web服务间调用

    备注:基于方法调用通常会与特定的程序语言耦合起来,而基于消息的调用则与具体的实现语言无关

### RESTAPI

>表征状态转移（Representational State Transfer），采用Web 服务使用标准的 HTTP 方法 (GET/PUT/POST/DELETE) 将所有 Web 系统的服务抽象为资源

**特点**

 * 网络上的 所有事物都可以被抽象为资源
 * 每一个资源都有唯一的资源标识,对资源的操作不会改变这些标识 
 * 所有的操作都是 无状态的 











