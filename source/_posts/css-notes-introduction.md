---
layout: post
title: css-notes-introduction
date: 2018-07-17
categories: 技术
---

### 前言

CSS(Cascading style sheets)是用于描述网页内容的语言;是Open Web Platform的主要组件之一。文章主要针对CSS做一次整理，以达到能够对CSS有大致地了解

### CSS主要内容

* CSS选择器
* CSS属性
* CSS布局
* CSS函数
* CSS动画
* CSS At-rules
* 媒体查询

### CSS选择器

### CSS属性组

##### 背景

* `background-attachment` - 设置背景图像是随对象内容滚动还是固定的
* `background-clip` -  设置背景相对对象内容的裁剪方式
* `background-color` - 设置背景颜色
* `background-image` - 设置背景图片
* `background-origin` - 设置背景的起始计算位置
* `background-position` - 设置背景图片的位置
* `background-repeat` - 设置背景图片是否平铺
* `background-size` - 设置背景尺寸大小

##### 边框

* `border-bottom` - 边框底部样式(同顶部,左侧,右侧)
* `border-color` - 边框颜色
* `border-image` - 边框图片
* `border-style` - 边框样式
* `box-shadow` - 边框阴影样式
* `border-radius` - 边框圆角样式

##### 文本

* `font-family` - 字体系列
* `font-size` - 字号
* `font-style` - 字体样式
* `font-weight` - 字体粗细
* `text-align` - 文本水平对齐方式
* `text-decoration` - 文本装饰效果
* `text-justify` - 文本对齐方式
* `text-transtorm` - 文本大小写
* `text-shadow` - 文字阴影

##### 超链接

* `target` - 链接打开方式

##### 列表

* `list-style-image` - 列表项标记为图像
* `list-style-type` - 列表标记类型
* `list-style-position` - 列表标记放置位置

##### 表格

* `border-collapse` - 是否合并表格边框
* `border-spacing` - 表格边框距离
* `caption-side` - 表格标题位置

### CSS布局

> CSS页面布局技术允许我们拾取网页中的元素，并且控制它们相对正常布局流、周边元素、父容器或者主视口/窗口的位置

##### **CSS布局包括哪些技术**

- 浮动
- 定位
- CSS 表格
- 弹性盒子
- 网格

##### CSS浮动 - position

> 定义：用于设置元素在HTML文档的定位方式,最终的位置由`top`, `right`, `bottom`, and `left`决定

​        position可选值：

> static  |  relative  |  absolute  |  sticky  |  fixed



##### 什么是BFC

##### CSS常见布局

[API参考](https://devdocs.io)



