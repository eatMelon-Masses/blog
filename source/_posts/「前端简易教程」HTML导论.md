---
layout: post
title: 「前端简易教程」HTML导论
date: 2018-05-05
categories: 技术
---

## 前言

该文档主要参考`webplatform`网站进行记录，这个项目是由`Adobe`,`Apple`,`Facebook`,`Google`,`HP`,`Intel`,`Microsoft`,`Mozilla`,`Nokia`, and `Opera – collaborated` with `W3C`等科技公司合作完成的，主要发布有关如何使用运行Web的技术的最新信息。

## 概述

### HTML概述

HTML(Hypertext Markup Language)是对于web页面的描述性语言

### HTML主要内容

* HTML元素
* HTML元素属性
* HTML APIs
* HTML Entities


### HTML基本元素

##### **DOCTYPE**

>文档类型说明,用于告诉浏览器如何解析web文档

* The HTML 4.01 strict doctype

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
```

* The HTML 4.01 transitional doctype

```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
```

* The HTML 4.01 frameset doctypes

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Frameset//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-frameset.dtd">
```

* The XHTML 1.0 strict doctypes

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
```

* The XHTML 1.0 transitional doctypes

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
    "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
```

* The XHTML 1.0 frameset doctypes

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Frameset//EN"
    "http://www.w3.org/TR/xhtml1/DTD/xhtml1-frameset.dtd">
```

* The HTML5 doctype

```html
<!DOCTYPE html>
```

[参考](https://webplatform.github.io/docs/guides/doctypes_and_markup_styles/)

##### HTML

> html标签是HTML文档的root标签，是除了<!DOCTYPE>外所有标签的容器

##### **head**

> head标签主要用于表示meta数据集合

**包含子标签**

- [`base`](https://webplatform.github.io/docs/html/elements/base)
- [`link`](https://webplatform.github.io/docs/html/elements/link)
- [`meta`](https://webplatform.github.io/docs/html/elements/meta)
- [`script`](https://webplatform.github.io/docs/html/elements/script)
- [`style`](https://webplatform.github.io/docs/html/elements/style)
- [`title`](https://webplatform.github.io/docs/html/elements/title)

##### **body**

> body标签主要包含用于展示在HTML文档页面的实体元素标签



### head标签说明

##### meta

* `name` - 设置HTML文档元数据

  >包括`application-name` , `author`，`description`，`generator`，`keywords`等属性

* `content` - 用于设置HTML元数据或HTTP头部信息值

* `http-equiv` - 用于设置HTTP头部信息

  > 包括`content-language`，`content-type`，`default-style`，`refresh`等属性

* `charset` - 设置HTML文档编码格式

### body标签说明

##### 文本标签

* 标题

  ```html
  <h1>Marking up textual content in HTML</h1>
  ```

* 段落

  ```html
  <p>This is a very short paragraph. It only has two sentences.</p>
  ```

* 引用

  ```html
  <blockquote cite="http://www.w3.org/TR/html401/">
      <p>This document obsoletes previous versions of HTML 4.0</p></blockquote>
  ```

* 预格式化文本

  ```html
  <pre><code class="language-c">
      int main(){}
  </code></pre>
  ```

* 短文本引用

  ```html
  <q lang="fr">c'est la vie</q>
  ```

* 文本强调

  ```html
  <strong>Warning!</strong>
  ```

* 小文本显示

  ```html
  <p><small>This content</small></p>
  ```

* 时间格式化

  ```html
  <p><time datetime="1978-06-27">June 27 1978 - my birthday</time>.</p>
  ```




##### 链接标签

> 链接是指向其他文档或资源的路径

* 链接标签案例

  ```html
  <p><a href="http://www.opera.com">Opera Software</a></p>
  ```

* 链接属性

  * href：存放目标资源链接地址或**锚ID**(用于页面内链接间跳转)
  * id ：链接唯一标识,可用于css样式描述或锚ID
  * class ：链接类名,可用于css样式描述
  * title :链接内容描述,在链接获取焦点事件时获取

* 链接事件

  * :link-----链接未被点击
  * :visited--链接已被点击
  * :hover----鼠标悬停于链接
  * :focus----鼠标焦点聚焦于链接
  * :active---链接被激活,于鼠标点击时刻

##### 列表标签

* 无序列表

  ```html
  <ul>
        <li>bread</li>
        <li>coffee beans</li>
        <li>milk</li>
        <li>butter</li>
      </ul>
  ```

* 有序列表

  ```html
  <ol>
        <li>Gather ingredients</li>
        <li>Mix ingredients together</li>
        <li>Place ingredients in a baking dish</li>
      </ol>
  ```

* 描述列表

  ```html
  <dl>
        <dt>Name</dt>
        <dd>Value</dd>
        <dt>Name</dt>
        <dd>Value</dd>
        <dt>Name</dt>
        <dd>Value</dd>
      </dl>
  ```


### HTML标签归类

##### 根元素

* `html`

##### 文档元数据

* `link`
* `meta`
* `style`

##### 内容分区

* `header`
* `nav`
* `section`
* `aside`
* `footer`
* `h1~h6`
* `article`
* `address`
* `hgroup`

##### 文本内容

* `main`
* `div`
* `p`
* `pre`
* `col`
* `ul`
* `li`
* `dl`
* `dt`
* `dd`
* `figure`
* `figcaption`
* `blockquote`
* `hr`

##### 内联文本语义

* `span`
* `a`
* `strong`
* `em`
* `q`
* `br`
* `markcode`
* `abbr`
* `b`
* `bdi`
* `bdo`
* `sub`
* `sup`
* `time`
* `i`
* `u`
* `cite`
* `data`
* `kbd`
* `nobr`
* `s`
* `samp`
* `tt`
* `var`
* `wbr`
* `rp`
* `rt`
* `rtc`
* `ruby`

##### 图片与多媒体

* `img`
* `audio`
* `video`
* `track`
* `map`
* `area`

##### 内嵌内容

* `iframe`
* `embed`
* `object`
* `param`
* `picture`
* `source`

##### 脚本

* `canvas`
* `noscript`
* `script`

##### 编辑标识

* `del`
* `Ins`

##### 表格

* `table`
* `caption`
* `thead`
* `tbody`
* `tfoot`
* `tr`
* `col`
* `colgroup`
* `th`
* `td`

##### 表单

* `form`
* `input`
* `textarea`
* `label`
* `button`
* `datalist`
* `fieldset`
* `legend`
* `meter`
* `optgroup`
* `option`
* `output`
* `progress`
* `select`

##### 交互元素

* `details`
* `summary`
* `dialog`
* `menu`

##### web组件

* `slot`
* `Template`

##### 过时标签

* `acronym`
* `applet`
* `basefont`
* `bgsound`
* `big`
* `blink`
* `center`
* `command`
* `content`
* `dir`
* `element`
* `font`
* `frame`
* `frameset`
* `image`
* `isindex`
* `keygen`
* `listing`
* `marquee`
* `menuitem`
* `multicol`
* `nextid`
* `nobr`
* `noembed`
* `noframes`
* `plaintext`
* `spacer`
* `strike`
* `shadow`
* `tt`
* `xmp`