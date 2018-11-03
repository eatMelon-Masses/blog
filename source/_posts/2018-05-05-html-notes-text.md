---
layout: post
title: html-notes-text
summary: 本章主要针对html标签中的文本标签进行学习总结.
featured-img: aaai
categories: html-notes
---


## 标签说明

### 标题

    <h1>Marking up textual content in HTML</h1>
    <h2>Introduction</h2>
    <h2>Space — the final frontier</h2>
    <h2>Block elements</h2>
    <h3>Page section headings</h3>
    <h3>Generic paragraphs</h3>
    <h3>Quoting other sources</h3>
    <h3>Preformatted text</h3>
    <h2>Inline elements</h2>

### 段落

    <p>This is a very short paragraph. It only has two sentences.</p>

### 引用

    <blockquote cite="http://www.w3.org/TR/html401/">
    <p>This document obsoletes previous versions of HTML 4.0,
    although W3C will continue to make those specifications and
    their DTDs available at the W3C website.</p>
    </blockquote>

### 预格式化文本

    <pre><code class="language-perl">
    sub slurp {
    my $filename = shift;
    my $file     = new FileHandle $filename;
    if ( defined $file ) {
      local $/;
      return <$file>;
    }
    return undef;
    };
    </code></pre>

### 短文本引用

    <q lang="fr">c'est la vie</q>

### 文本强调

    <em>Please</em>
    <i lang="fr">je ne sais quoi</i>
    <strong>Warning!</strong>
    <b>string</b>

### 小文本显示

    <p><small>This content</small></p>

### 时间格式化显示

    <p>I was born on the <time datetime="1978-06-27">27<sup>th</sup> June 1978</time>.</p>
    <p><time datetime="1978-06-27">June 27 1978 - my birthday</time>.</p>
    <p><time datetime="1978-06-27T21:00">9pm on my birthday</time>.</p>
    <p><time datetime="21:00">9pm</time>.</p>
    <p><time datetime="1978-06-27T21:00:00.006-08:00">9pm and 6 milliseconds on my birthday, in Pacific standard time</time>.</p>
    <p>Published on <time datetime="2011-07-20" pubdate>July 27<sup>th</sup> 2011</time>.</p>
