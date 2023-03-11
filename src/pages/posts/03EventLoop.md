---
layout: '../../layouts/MarkdownPost.astro'
title: 'EventLoop事件循环'
pubDate: 2023-03-11
description: '面试中被问到这道题'
author: 'S'
cover:
    url: 'https://pic2.zhimg.com/80/v2-0359c5bd53e7222d579429c1641af6f1_720w.webp'
    square: 'https://pic2.zhimg.com/80/v2-0359c5bd53e7222d579429c1641af6f1_720w.webp'
    alt: 'cover'
tags: ["前端", "面试"]
theme: 'light'
featured: true
---

## 什么是事件循环

js是一门单线程的语言，而通常单线程会产生许多问题，如线程任务阻塞。JS的事件循环（实现单线程的非阻塞方法）就是为了解决这一问题而诞生的。

js的任务可以分为同步任务和异步任务。
1. 同步任务：立即执行的任务,大部分代码都是同步任务。
2. 异步任务：ajax网络请求以及计时器等。异步任务还可以分为微任务和宏任务。
    - 微任务：线程的切换。主要有Promise、MutaionObserver（监视对dom树所作的更改的能力）、process.nextTick（nodejs的异步API）。
    - 宏任务：进程的切换。主要有计时器、事件、script（外层同步代码）。

## 执行顺序

先执行同步任务，再执行异步任务，异步任务中，先执行一个宏任务，宏任务中有微任务的，将其放入至微任务的任务队列，当前宏任务执行完毕后，将微任务队列中的微任务依次执行完毕。

