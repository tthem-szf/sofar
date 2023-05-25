---
layout: '../../layouts/MarkdownPost.astro'
title: 'NodeJsDay3'
pubDate: 2023-01-12
description: '愿上帝赐予我从容去接受我不能改变的，并赐予我勇气去改变我可以改变的,并赐予我智慧去分辨这两者的区别'
author: 'S'
cover:
    url: 'https://www.opus-software.com.br/wp-content/uploads/2018/09/nodejs.jpg'
    square: 'https://www.opus-software.com.br/wp-content/uploads/2018/09/nodejs.jpg'
    alt: 'cover'
tags: ["所有博客","前端","读书"]
theme: 'dark'
featured: true
---

## Javascript 有哪些模块化规范
1. AMD和CMD，适用于浏览器端的Javascript模块。
1. CommonJs(前一节讲的模块化规范)，适用于服务器端的模块化规范。
1. ES6模块化规范
    - 导入 import关键字。
    - 导出 export关键字。
    - nodeJs中如何使用ES6模块化规范：在package.json的根节点中添加"type":"module"节点。

## ES6的基本语法

1. 默认导出与默认导入
    - 默认导出：**export default {}** 花括号可加可不加，只允许使用一次，否则会把前面的默认导出给覆盖。
    - 默认导入：**import 接受名称 from '模块标识符（必须加.js后缀）'**。接受名称可以自定义。

2. 按需导出与按需导入
    - 按需导出：**export 按需导出的成员**  
    - 按需导入：**import {接受名称1,接受名称2} from '模块标识符'**（必须加.js后缀。接受名称必须和按需导出的一致，当然也可以用as关键字进行重命名。

##  Promise 和EventLoop





## 读书分享

"直接来自感官上的认识很容易和他人分享，而思想上的体验往往难以用语言表达"。这一点深有体会，与朋友交谈，大多是聊正在经历的事情，或者已经发生过的事情。究其原因，是因为感官是客观的，思想是主观的，并且，如果和他人说自己的思想，会有一种说教的意味，很多时候，人们往往更相信自己的经验，而非他人的说。 但这也并不意味着思想就无法分享，我很喜欢罗翔老师的原因之一就是他总是能用简洁的语言引人深思。

