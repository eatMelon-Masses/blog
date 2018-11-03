---
layout: post
title: html-notes-link
summary: 本章主要针对html标签中的链接标签进行学习总结.
featured-img: aaal
categories: 随笔
---


## 标签说明

>Links are parts of an HTML document that point to other resources — other HTML documents, >text files, PDF files, etc.
>链接是指向其他文档或资源的路径

#### 链接案例
    <p><a href="http://www.opera.com">Opera Software</a></p>
>**描述**:
>当访问者激活链接则会跳转到opera网站


#### 链接属性
> - href：存放目标资源链接地址或**锚ID**(用于页面内链接间跳转)
> - id ：链接唯一标识,可用于css样式描述或锚ID
> - class ：链接类名,可用于css样式描述
> - title :链接内容描述,在链接获取焦点事件时获取

#### 链接事件
> - :link-----链接未被点击
> - :visited--链接已被点击
> - :hover----鼠标悬停于链接
> - :focus----鼠标焦点聚焦于链接
> - :active---链接被激活,于鼠标点击时刻


[**参考文档**](https://webplatform.github.io/docs/guides/html_links/)
