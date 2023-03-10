---
layout: '../../layouts/MarkdownPost.astro'
title: '我的第一篇博客'
pubDate: 2023-03-10
description: '试试看能不能发上去'
author: 'S'
cover:
    url: 'https://w.wallhaven.cc/full/j3/wallhaven-j3m8y5.png'
    square: 'https://w.wallhaven.cc/full/j3/wallhaven-j3m8y5.png'
    alt: 'cover'
tags: ["生活", "前端学习进阶", "思考与观点"]
theme: 'light'
featured: false
---

Hello, have a nice day!(这段文字居中对齐了)

再来一段文字,看看效果。

来一段今天写的js算法题，题目名称是：求字符串的最长不重复字串的长度。
``` js
//用滑动窗口的方式实现
    function lengthOfLongestSubstring(str) {
      //首先定义左指针和右指针以及最长长度,分别初始化为0
      let lp = 0;
      let rp = 0;
      let maxLength = 0;
      let map = new Map();//定义一个空的map结构,用于存放当前最长的无重复字串

      while (rp < str.length) {
        //1判断map中是否有当前右指针指向的字符
        if (map.has(str[rp])) {
          //1.1如果有,更新左指针的位置为 map中当前右指针的下一位索引(窗口滑动)
          lp = map.get(str[rp]) + 1;
          //1.2将map中左指针以前的值删除掉   str[]
          for (let i = lp - 1; i >= map.get(str[rp]); i--) {
            map.delete(str[i]);
          }
        }
        //2将当前的右指针对应的值和索引放进map当中
        map.set(str[rp], rp);
        //3更新右指针的值++
        rp++;
        //4更新最大长度的值
        maxLength = Math.max(maxLength, rp - lp);
        // maxLength = maxLength < map.length ? map.length : maxLength;
      }
      return maxLength;
    }

    console.log(lengthOfLongestSubstring('abcabcb')); //3
```

再来一张图片

![躺在花丛中的宇航员](https://w.wallhaven.cc/full/1p/wallhaven-1p398w.jpg)

试试看本地图片。好吧，看来本地的图片暂时用不了,不加任何东西,图片默认就这么大

![蓝天之下的蓝色飞机](../upload/plane.png)

可以将图片的宽度占满整个屏幕 |wide

![红色的法拉利赛车 |wide](https://w.wallhaven.cc/full/1k/wallhaven-1ky369.jpg)

再试试同段落宽度一致的图片 |inline 

![红色的法拉利赛车 |inline](https://w.wallhaven.cc/full/1k/wallhaven-1ky369.jpg)

## 来一个二级标题吧

下面再写一些文字（如果标题下面没有写文字，就会自动顶到左边）

### 三级标题

#### 四级标题

# 一级标题 好吧 所有的标题大小都一样    



