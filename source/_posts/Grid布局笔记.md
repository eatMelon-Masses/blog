---
layout: post
title: Grid布局笔记
date: 2019-03-07
categories: 技术
---

#### 前言
在开始学习Grid布局之前，我们首先回顾一下：在前端开发中，我们能够通过怎样的布局完成页面的构建呢？
* Normal Flow - 正常流布局
* Floats - 浮动布局
* Position - 定位布局
* multiple-column layout - 多列布局
* Flewbox布局
* Grid布局（[Grid入门学习教程][1]）

[参考CSS布局网站][2]

接着，小编会大致描述一下Grid布局：

CSS Grid布局是一个二维的基于网格的布局系统，它的目标是完全改变我们基于网格的用户界面的布局方式；在CSS Grid布局中，基本术语包括：
* 网格容器 - Grid Container
* 网格项 - Grid Item
* 网格线 - Grid Line
* 网格轨道 - Grid Track
* 网格单元格 - Grid Cell
* 网格区域 - Grid Area

#### 如何创建Grid布局页面
* 定义Grid容器
  ```css
  .container{
	  display: grid; 
  }
  ```

* 定义Grid列

   ```css
   .container{
      display: grid;
      grid-template-columns: 200px 200px 200px;
   } 
   ```

   

[Grid布局中文教程][3]
[Grid布局案例][4]

#### Flexbox和Grid比较

* http://cssgridgarden.com/
* https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout
* https://www.html.cn/archives/8510
* https://www.html.cn/archives/8706