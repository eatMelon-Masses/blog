---
layout: post
title: 「译」困难的现代JavaScript开发
date: 2019-02-26
categories: 技术
---

最近经常听到有人吐槽JavaScript开发变得越来越复复杂。我也对刚刚开始学习JavaScript的人表示同情。

> It’s not uncommon these days to see people complaining about just how complex JavaScript development seems to have become. I can have some sympathy with that view when it’s coming from someone new to the language.
> Ads by Hooly

如果你正在学习JS，你需要花很长时间才能认识到生态系统的巨大规模，以及了解（至少从概念上）系统构建中的大量模块

> If you’re learning JS, it won’t take long for you to be exposed to the enormity of the ecosystem and the sheer number of moving pieces you need to understand (at least conceptually) to build a modern web application.

包管理模块，标记，转换，模块组合，源映射，框架，单元测试，热更新…不可否认的是，这比仅仅在页面内添加几个标签以及通过FTP映射到服务器内更为复杂

> Package management, linting, transpilation, module bundling, minification, source maps, frameworks, unit testing, hot reloading… it can’t be denied that this is a lot more complex that just including a couple script tags in your page and FTPing it up to the server.



Some people who have been involved with web development for years are still pining for those ‘good old days’, and it’s this kind of complaining that I have much less sympathy for. One such comment I read this last week claimed that web development had been hijacked by those who enjoy using the command line and writing JSON config files.

For a long time, JavaScript was looked upon by many as a joke; a toy language whose only real use was to add non-essential eye-candy, such as mouseover changes, and was often a source of weird errors and broken pages. The language is still not taken seriously by some today, despite having made much progress since those early days. It’s not hard to have some sympathy with PHP developers.

For better or for worse, JavaScript was (and still is) the only language supported natively by the vast majority of web browsers. The community has worked hard to improve the language itself, and to provide the tooling to help build production-grade apps. I find it ironic that now people attack JavaScript development for being “too complicated”. Unfortunately, you just can’t have it both ways.

JavaScript developers are now some of the most in-demand (and well compensated) in the industry. Is there any reason to think that it should be ‘easy’? Try talking to a Java or a .NET developer; both these technologies have large ecosystems and build tooling setups for developing production-quality apps. And as for config files, many Java tools have XML files coming out of their… ears.

A lot of JavaScript tutorials often include things like module bundling and transpilation, because writing modular code with the latest language features are skills that are in demand in the job market. They are the necessary pieces for building large, complex applications in a team environment. Keep in mind that a lot of these build tools and development techniques are entirely optional. No one is forcing you to use them for your projects. Like all tools, they are a trade-off: they solve specific problems, at the cost of increasing your project’s complexity (in one form or another). Nothing is stopping you writing plain old ES5 JavaScript files and linking them to your HTML with script tags. You can even pull in frameworks like React and Vue from CDNs if you want to.

Are you happy with JavaScript’s evolution, or has modern web development taken all the joy out of coding for you? I’d be very interested to hear your thoughts on this, so please let me know in the comments or on Twitter.

PS. If you are new to JavaScript development or are coming back to the language after an extended break, be sure to check back tomorrow for our guide to the anatomy of a modern JavaScript application!

[原文链接](https://www.sitepoint.com/modern-javascript-development-hard)