---
layout: post
title: html-notes-meta
summary: 记录meta标签的一些常见使用.
featured-img: aaaj
categories: html-notes
---



## meta标签简介
说明：提供有关页面的数据信息，用于浏览器解析页面

## meta标签常见使用

 - charset：设置页面的字符集编码
    >&lt;head&gt;
    >&lt;meta charset="UTF-8"&gt;
    >&lt;/head&gt;

 - http-equiv:实现content属性/值的http头，可模拟http响应头
   1. content-type:设置页面的字符集编码
   `<meta http-equiv="content-type" content="text/html; charset=UTF-8">`
   2. default-style:规定要使用的预定义的样式表
   `<meta http-equiv="default-style" content="the document's preferred stylesheet">`
   3. refresh:设置页面的刷新时间间隔
    `<meta http-equiv="refresh" content="300">`
    

 - name：规定了content属性值名称
    1. application-name:规定页面所代表的 Web 应用程序的名称
    2. author:规定文档作者名称
    `<meta name="author" content="Hege Refsnes">`
    3. description:规定页面描述
    ` <meta name="description" content="Free web tutorials">`
    4. keywords:规定页面关键字
     ` <meta name="keywords" content="HTML, meta tag, tag reference">`
