---
layout:     post
title:      JavaScript的世界
date:       2018-03-15 00:00:00
author:     Joy Zheng
summary:    world of JavaScript
comments:   true
categories: Tech
thumbnail:  cogs
tags:
 - JavaScript
 - Web Frontend
---
#### 理解JavaScript世界的一张重要的图：
![Thumper](https://images2017.cnblogs.com/blog/1235327/201709/1235327-20170913143257594-424466016.png)

### 对上面图的描述如下：
 1. JS中万物接对象（虽然这个说法是不准确的因为`null`严格意义上并不是对象而会被误判断为`object`）
 
    方法`Function`是对象，方法的原型`Function.prototype`是对象。因此，它们都会具有对象共有的特点。
    
    即：对象具有属性`__proto_`_，可称为隐式原型，一个对象的隐式原型指向构造该对象的构造函数的原型，这也保证了实例能够访问在构造函数原型中定义的属性和方法。
 2. 方法`Function`
    
     `Function`这个特殊的对象，除了和其他对象一样有上述`_proto_`属性之外，还有自己特有的属性——原型属性`prototype`，这个属性是一个指针，指向一个对象，这个对象的用途就是包含所有实例共享的属性和方法（我们把这个对象叫做原型对象）。原型对象也有一个属性，叫做`constructor`，这个属性包含了一个指针，指回原构造函数。
 
 3. 构造函数`Foo()`
    
    构造函数的原型属性`Foo.prototype`指向了原型对象，在原型对象里有共有的方法，所有构造函数声明的实例（这里是`f1`，`f2`）都可以共享这个方法
 4. 原型对象`Foo.prototype`
    
    `Foo.prototype`保存着实例共享的方法，有一个指针`constructor`指回构造函数。
 5. 实例
    
    `f1`和`f2`是`Foo`这个对象的两个实例，这两个对象也有属性`__proto__`，指向构造函数的原型对象，这样子就可以像上面所说的访问原型对象的所有方法啦。
 6. 构造函数`Foo()`除了是方法，也是对象啊，它也有`__proto__`属性，指向谁呢？
    
    指向它的构造函数的原型对象呗。函数的构造函数不就是`Function`嘛，因此这里的`__proto__`指向了`Function.prototype`。
    其实除了`Foo()`，`Function()`, `Object()`也是一样的道理。
 7. 原型对象也是对象啊，它的`__proto_`_属性，又指向谁呢？
    
    同理，指向它的构造函数的原型对象呗。这里是`Object.prototype`.
 8. `Object.prototype`的`__proto__`属性指向`null`。
    
#### 总结：
1. 对象有属性`__proto__`,指向该对象的构造函数的原型对象。
2. 方法除了有属性`__proto__`,还有属性`prototype`，`prototype`指向该方法的原型对象




