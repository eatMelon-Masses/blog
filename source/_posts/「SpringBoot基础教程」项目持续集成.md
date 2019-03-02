---
layout: post
title: 「SpringBoot基础教程」项目持续集成
date: 2019-02-23
categories: spring
---

这一小节其实和SpringBoot关系不是特别大，但是软件开发和建筑不一样，建筑要求的是完美，而软件更多的是靠迭代去打磨产品，所以我们就需要持续集成去打造产品迭代的环境

#### Travis-CI介绍

**Travis CI**是在软件开发领域中的一个在线的，分布式的持续集成服务，用来构建及测试在GitHub托管的代码。这个软件的代码同时也是开源的，可以在GitHub上下载到，尽管开发者当前并不推荐在闭源项目中单独使用它。它提供了多种编程语言的支持，包括Ruby、JavaScript、Java、Scala、PHP、Haskell和Erlang在内的多种语言[[5\]](https://zh.wikipedia.org/wiki/Travis_CI#cite_note-infoq-5)。许多知名的开源项目使用它来在每次提交的时候进行构建测试，比如Ruby on Rails，Ruby和Node.js

#### 添加Travis-CI持续构建服务

* 将Github内构建项目添加到Travis-CI中[网站地址](https://travis-ci.com)

* 项目内添加`.travis.yml`配置文件

* 添加配置信息

  ```java
  language: java
  jdk:
    - oraclejdk8
  ```

* 项目添加徽章信息，用于检测项目是否构建成功