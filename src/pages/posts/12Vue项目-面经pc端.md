---
layout: '../../layouts/MarkdownPost.astro'
title: '12Vue项目-面经pc端'
pubDate: 2023-04-22
description: '用到了echarts、vuex、elementUI，基本的增删改查使用vue实现'
author: 'S'
cover:
    url: 'https://images.unsplash.com/photo-1679678691014-eba529defb2c?ixlib=rb-4.0.3&ixid=MnwxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1169&q=80'
    square: 'https://images.unsplash.com/photo-1679678691014-eba529defb2c?ixlib=rb-4.0.3&ixid=MnwxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1169&q=80'
    alt: 'cover'
tags: ["所有博客","前端", "面试"]
theme: 'light'
featured: true
---

## 项目功能

1. 登录页
   1. 登录页elementUI布局
   2. 登录和重置按钮的实现
2. 后台管理页
   1. 数据看板
      1. 布局
      2. echarts
      3. 
   2. 面经管理系统



### 项目历程

1. 先配置路由，在一个新建的文件夹中配置路由的步骤为：先安装vuerouter包，然后在router中的index.js引入、配置、暴露（配置要根据组件的父子层级来定义，记得写<router-view></router-view>），然后在main.js中引入router。暂时不需要写router-link，因为后面用elementUI会自动完成跳转功能。
2. 还是配置路由，因为首页是默认页面，所以首页的路径改为'/'，然后需要给home写一个重定向定向到chart1。
3. 引入element-ui，我采用的是全局引用。yarn add element-ui -S
4. 在utils设置request.js设置接口请求工具axios，设置请求拦截器和响应拦截器。
5. 在utils设置storage.js设置本地存储token工具，写三个函数：setToken,getToken和delToken.
6. 登录界面ui。先写好html结构。再设置相应的样式，要注意：
   1. ::v-deep 是 Vue.js 框架中的一个特殊选择器，用于在 scoped 样式中穿透子组件的样式隔离。
   2. 如果想要让子盒子垂直居中，就需要给父盒子设置对应的高度。
   3. background-size: cover;用于指定背景图片（或背景图像）在元素的背景区域中的大小，通过使用 `cover`，可以确保背景图片始终占据整个背景区域，而不会出现任何未使用的空白区域。
7. 登录的表单校验规则：找到饿了吗官网的form，复制对应的表单，然后在data里定义表单绑定元素和校验规则数组，然后在模板中的外层form绑定这两项，里面具体的el-input标签修改其label标签和prop绑定。
8. 登录的按钮跳转。在登录按钮的点击事件绑定一个函数，先校验输入框格式是否正确，如果正确，就调用登录接口（这里在api文件夹新建一个user.js接口文件，用于暴露各种管理员用户信息请求接口），因为在request.js的相应拦截器中设置了错误的处理方式，所以一旦请求错误就不会执行以后的代码，于是可以省略对于请求结果的判断，直接在请求以后跳转。
9. 重置清空按钮。参考饿了吗的表单函数resetFields();
10. 登录的Token请求（vuex+本地存储）：vuex用于保存token的状态，所以在登录的请求成功时，将请求返回的token值传入到vuex的state中，在vuex的token状态设置函数里头再调用（写一下）本地tokne存取删的函数。具体如何实现vuex？
    1. 新建一个store文件夹，里头的index.js用于管理所有的vuex模块并暴露出来，引入vue，vuex（3版本的）以及各个子vuex模块。
    2. 在子模块中完成token的更新与删除，然后暴露出来。
    3. main.js引入store，并写到vue入口构建函数中。
    4. 登录成功的地方调用commit,里面有两个参数，第一个参数以.../...的格式获取具体的函数名，第二个参数是传入给vuex的参数值
11. token登录拦截访问，如果当前访问的页面不是登录页面，并且没有token，就拦截访问，并跳转到登录页面。
12. 首页布局。这里太复杂了，我先copy一下写好的



