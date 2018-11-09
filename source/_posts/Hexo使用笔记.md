---
layout: post
title: Hexo使用笔记
date: 2018-11-09
categories: 技术
---

### 前言

##### **什么是Hexo**

Hexo是一个简洁而高效的博客框架；使用markdown渲染引擎将Hexo主题生成静态页面

##### **Hexo资料**

* [官方文档](https://hexo.io/zh-cn/docs/)
* [Github仓库](https://github.com/hexojs/hexo)

### Hexo基本使用

* Hexo安装`npm install hexo-cli -g`
* 创建Hexo项目`hexo init [folder]`
* Hexo项目启动`hexo server`
* Hexo项目部署`hexo deploy`

###  Hexo集成Github Pages

* 创建GIthub仓库

* 创建Hexo本地项目

* 安装Hexo部署插件`npm install hexo-deployer-git --save`

* 修改_config.yml部署相关信息

  ```yaml
  deploy:
    type: git
    repo: <repository url>
    branch: [branch]
    message: [message]
  ```

* 发布Hexo静态页面`hexo deploy`

### Hexo theme 制作

* 创建Hexo项目
* `themes`目录下创建自定义主题目录
* 修改自定义主题样式

### Hexo 插件

