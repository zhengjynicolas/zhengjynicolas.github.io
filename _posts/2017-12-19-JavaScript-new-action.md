---
layout:     post
title:      JavaScript中new操作都干了些什么？
date:       2017-12-19 20:13:19
author:     Joy Zheng
summary:    JavaScript中的操作符new与其他面向对象语言中的new机制完全不同。
comments:   true
categories: Tech
thumbnail:  cogs
tags:
 - JavaScript
 - Web Frontend
---

JavaScript中的操作符new与其他面向对象语言中的new机制完全不同。

首先，在JavaScript中并没有所谓的`构造函数`，因为在JavaScrpit中没有类（class）的机制，

即使是被new调用的Function也不属于任何类，他们只是一些`普通函数`而已。

所以，在JavaScript只用new实现的<构造调用>。

new操作符最终执行的结果就是初始化一个新创建的对象。



那么，在用new调用函数，发生构造调用的时候又做了些什么事呢？

  1. 创建(或者说创造)一个全新的对象。
  2. 这个新对象会被[[Prototype]]链接。
  3. 函数调用时的this会绑定到这个新对象上。
  4. new调用的函数会自动的返回一个创建好的新对象（前提是这个函数没有返回其他对象）。