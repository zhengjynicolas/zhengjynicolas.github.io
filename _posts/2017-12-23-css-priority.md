---
layout:     post
title:      CSS选择器权重/优先级
date:       2017-12-23 16:46:00
author:     Joy Zheng
summary:    CSS优先级
comments:   true
categories: Tech
thumbnail:  cogs
tags:
 - css
 - Web Frontend
---

CSS优先级如下：

!important > 内嵌样式 > ID > class | 伪类 | 属性选择 > 元素 > 继承 | 通配符。

**注意**：!important一般情况下不推荐使用。

CSS权重：

![Thumper](http://www.nowamagic.net/csszone/images/priority_rules_1.jpg)

4个等级的定义如下：

  1. 第一等：代表内联样式，如: style=””，权值为1000。
  2. 第二等：代表ID选择器，如：#content，权值为100。
  3. 第三等：代表类，伪类和属性选择器，如.content，权值为10。
  4. 第四等：代表类型选择器和伪元素选择器，如div p，权值为1。


例如上图为例，其中#NAV为二等选择器，.ACTIVE为三等选择器，UL、LI和A为四等选择器。则整个选择器表达式的特殊性的值为1*100+1*10+3*1=113

下面是一些计算示例：

![Thumper](http://www.nowamagic.net/csszone/images/priority_rules_2.jpg)

**注意**：通用选择器（*），子选择器（>）和相邻同胞选择器（+）并不在这四个等级中，所以他们的权值都为0。