---
layout: post
title: Flexbox布局笔记
date: 2019-03-13
categories: 技术
---

长久以来，唯一可用的且有稳定的跨浏览器兼容性的能用来构建 CSS 布局的工具只有 floats 和 positioning；但是这种布局方式也有着自身的局限性，例如：
* 在父内容里面垂直居中一个块内容
* 使容器的所有子项占用等量的可用宽度/高度，而不管有多少宽度/高度可用
* 使多列布局中的所有列采用相同的高度，即使它们包含的内容量不同

### flexbox基本术语

* flex-direction：row | row-reverse | column | column-reserve
* flex-wrap: wrap | no-wrap | wrap-reverse
* flex-grow: 
* flex-shrink
* flex-basis
* flex

### 如何实现flexbox布局

1. 指定容器布局为flex

* [参考文档](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Flexbox)
* [Flexbox概念](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)
* [Flexbox案例](http://www.ruanyifeng.com/blog/2015/07/flex-examples.html)