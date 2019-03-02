---
layout: post
title: 「Vue学习指南」基础教程
date: 2019-02-25
categories: 技术
---

>本指南会基于Vue.js和Google blogger API创建博客这一案例，学习Vue的一些知识点

#### Vue安装

* script标签引入

  ```
  <script src="https://vuejs.org/js/vue.js"></script>
  ```

* npm依赖安装

  ```
  npm install vue
  ```

#### Vue模板语法

* 动态文本

  ```html
  <span>Message: {{ msg }}</span>
  ```

* 计算属性

  ```html
  <div id="example">
    <p>Original message: "{{ message }}"</p>
    <p>Computed reversed message: "{{ reversedMessage }}"</p>
  </div>
  ```

  ```javascript
  var vm = new Vue({
    el: '#example',
    data: {
      message: 'Hello'
    },
    computed: {
      // 计算属性的 getter
      reversedMessage: function () {
        // `this` 指向 vm 实例
        return this.message.split('').reverse().join('')
      }
    }
  })
  ```

* class动态绑定

  ```html
  <div v-bind:class="{ active: isActive }"></div>
  ```

* style动态绑定

  ```html
  <div v-bind:style="styleObject"></div>
  ```

* 条件渲染

  ```html
  <h1 v-if="awesome">Vue is awesome!</h1>
  ```

* 列表渲染

  ```html
  <ul id="example-2">
    <li v-for="(item, index) in items">
      {{ parentMessage }} - {{ index }} - {{ item.message }}
    </li>
  </ul>
  ```

#### Vue实例

```javascript
var vm = new Vue({
  data: {
    a: 1
  },
  created: function () {
    // `this` 指向 vm 实例
    console.log('a is: ' + this.a)
  }
})
```

#### Vue事件处理

```html
<div id="example-2">
  <button v-on:click="greet">Greet</button>
</div>
```

```javascript
var example2 = new Vue({
  el: '#example-2',
  data: {
    name: 'Vue.js'
  },
  methods: {
    greet: function (event) {
      // `this` 在方法里指向当前 Vue 实例
      alert('Hello ' + this.name + '!')
      // `event` 是原生 DOM 事件
      if (event) {
        alert(event.target.tagName)
      }
    }
  }
})
```

#### Vue组件

* 组件定义

  ```javascript
  Vue.component('blog-post', {
    props: ['post'],
    template: `
      <div class="blog-post">
        <h3>{{ post.title }}</h3>
        <div v-html="post.content"></div>
      </div>
    `
  })
  ```

* 组件注册

  ```javascript
  Vue.component('my-component-name', { /* ... */ })
  ```

  





