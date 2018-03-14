---
layout:     post
title:      CSS选择器总结
date:       2018-02-03 20:24:00
author:     Joy Zheng
summary:    CSS选择器
comments:   true
categories: Tech
thumbnail:  cogs
tags:
 - css
 - Web Frontend
---

**ID选择器：**

|选择器|例子|例子描述|CSS|
|-|-|-|-|
|[#id][1]|#firstname|选择id="firstname" 的所有元素。|1|



----------


**类选择器：**

|选择器|例子|例子描述|CSS|
|-|-|-|-|
|[.class][2]|.intro|选择 class="intro" 的所有元素。|1|


----------


**属性选择器：**

|选择器|例子|例子描述|CSS|
|-|-|-|-|
|[\[attribute\]][3] |[target]|选择带有 target 属性所有元素。|2|
|[\[attribute=value\]][4]|[target=_blank]|选择 target="_blank" 的所有元素。|2|
|[\[attribute~=value\]][5]|[title~=flower]|选择 title 属性包含单词 "flower" 的所有元素。|2|
|[\[attribute\|=value\]][6]|[lang\|=en]|选择 lang 属性值以 "en" 开头的所有元素。该值必须是整个单词，比如 lang="en"，或者后面跟着连字符，比如 lang="en-us"。|2|
|[\[attribute^=value\]][7]|a[src^="https"]|选择其 src 属性值以 "https" 开头的每个 <a> 元素。|3|
|[\[attribute$=value\]][8]|a[src\$=".pdf"]|选择其 src 属性以 ".pdf" 结尾的所有 <a> 元素。|3|
|[\[attribute*=value\]][9]|a[src*="abc"]|选择其 src 属性中包含 "abc" 子串的每个 <a> 元素。|3|


----------


**伪类选择器：**

|选择器|例子|例子描述|CSS|
|-|-|-|-|
|[:link][10]|a:link|选择所有未被访问的链接。|1|
|[:visited][11]|a:visited|选择所有已被访问的链接。|1|
|[:active][12]|a:active|选择活动链接。|1|
|[:hover][13]|a:hover|选择鼠标指针位于其上的链接。|1|
|[:focus][14]|input:focus|选择获得焦点的 input 元素。|2|
|[:first-letter][15]|p:first-letter|选择每个 <p> 元素的首字母。|1|
|[:first-line][16]|p:first-line|选择每个 <p> 元素的首行。|1|
|[:first-child][17]|p:first-child|选择属于父元素的第一个子元素的每个 <p> 元素。|2|
|[:before][18]|p:before|在每个 <p> 元素的内容之前插入内容。|2|
|[:after][19]|p:after|在每个 <p> 元素的内容之后插入内容。|2|
|[:lang(language)][20]|p:lang(it)|选择带有以 "it" 开头的 lang 属性值的每个 <p> 元素。|2|
|[:first-of-type][21]|p:first-of-type|选择属于其父元素的首个 <p> 元素的每个 <p> 元素。|3|
|[:last-of-type][22]|p:last-of-type|选择属于其父元素的最后 <p> 元素的每个 <p> 元素。|3|
|[:only-of-type][23]|p:only-of-type|选择属于其父元素唯一的 <p> 元素的每个 <p> 元素。|3|
|[:only-child][24]|p:only-child|选择属于其父元素的唯一子元素的每个 <p> 元素。|3|
|[:nth-child(n)][25]|p:nth-child(2)|选择属于其父元素的第二个子元素的每个 <p> 元素。|3|
|[:nth-last-child(n)][26]|p:nth-last-child(2)|同上，从最后一个子元素开始计数。|3|
|[:nth-of-type(n)][27]|p:nth-of-type(2)|选择属于其父元素第二个 <p> 元素的每个 <p> 元素。|3|
|[:nth-last-of-type(n)][28]|p:nth-last-of-type(2)|同上，但是从最后一个子元素开始计数。|3|
|[:last-child][29]|p:last-child|选择属于其父元素最后一个子元素每个 <p> 元素。|3|
|[:root][30]|:root|选择文档的根元素。|3|
|[:empty][31]|p:empty|选择没有子元素的每个 <p> 元素（包括文本节点）。|3|
|[:target][32]|#news:target|选择当前活动的 #news 元素。|3|
|[:enabled][33]|input:enabled|选择每个启用的 input 元素。|3|
|[:disabled][34]|input:disabled|选择每个禁用的 input 元素|3|
|[:checked][35]|input:checked|选择每个被选中的 input 元素。|3|
|[:not(selector)][36]|:not(p)|选择非 <p> 元素的每个元素。|3|
|[::selection][37]|::selection|选择被用户选取的元素部分。|3|


----------


**元素选择器：**

|选择器|例子|例子描述|CSS|
|-|-|-|-|
|[element][38]|p|选择所有 <p> 元素。|1|
|[element,element][39]|div,p|选择所有 <div> 元素和所有 <p> 元素。|1|
|[element element][40]|div p|后代选择器，选择 <div> 元素内部的所有 <p> 元素。|1|
|[element>element][41]|div>p|子元素选择器，选择父元素为 <div> 元素的所有 <p> 元素。|2|
|[element+element][42]|div+p|相邻兄弟选择器，选择紧接在 <div> 元素之后的所有 <p> 元素。|2|
|[element1~element2][43]|p~ul|相邻兄弟选择器，选择前面有 <p> 元素的每个 <ul> 元素。|3|


----------


**通配符选择器：**

|选择器|例子|例子描述|CSS|
|-|-|-|-|
|[\*][44]|\*|选择所有元素。|2|


*CSS优先级*

!important > 内嵌样式 > ID > class，伪类 ，属性选择 > 元素 > 继承，通配符。


  [1]: http://www.w3school.com.cn/cssref/selector_id.asp
  [2]: http://www.w3school.com.cn/cssref/selector_class.asp
  [3]: http://www.w3school.com.cn/cssref/selector_attribute.asp
  [4]: http://www.w3school.com.cn/cssref/selector_attribute_value.asp
  [5]: http://www.w3school.com.cn/cssref/selector_attribute_value_contain.asp
  [6]: http://www.w3school.com.cn/cssref/selector_attribute_value_start.asp
  [7]: http://www.w3school.com.cn/cssref/selector_attr_begin.asp
  [8]: http://www.w3school.com.cn/cssref/selector_attr_begin.asp
  [9]: http://www.w3school.com.cn/cssref/selector_attr_contain.asp
  [10]: http://www.w3school.com.cn/cssref/selector_link.asp
  [11]: http://www.w3school.com.cn/cssref/selector_visited.asp
  [12]: http://www.w3school.com.cn/cssref/selector_active.asp
  [13]: http://www.w3school.com.cn/cssref/selector_hover.asp
  [14]: http://www.w3school.com.cn/cssref/selector_focus.asp
  [15]: http://www.w3school.com.cn/cssref/selector_first-letter.asp
  [16]: http://www.w3school.com.cn/cssref/selector_first-line.asp
  [17]: http://www.w3school.com.cn/cssref/selector_first-child.asp
  [18]: http://www.w3school.com.cn/cssref/selector_before.asp
  [19]: http://www.w3school.com.cn/cssref/selector_after.asp
  [20]: http://www.w3school.com.cn/cssref/selector_lang.asp
  [21]: http://www.w3school.com.cn/cssref/selector_first-of-type.asp
  [22]: http://www.w3school.com.cn/cssref/selector_last-of-type.asp
  [23]: http://www.w3school.com.cn/cssref/selector_only-of-type.asp
  [24]: http://www.w3school.com.cn/cssref/selector_only-child.asp
  [25]: http://www.w3school.com.cn/cssref/selector_nth-child.asp
  [26]: http://www.w3school.com.cn/cssref/selector_nth-last-child.asp
  [27]: http://www.w3school.com.cn/cssref/selector_nth-of-type.asp
  [28]: http://www.w3school.com.cn/cssref/selector_nth-last-of-type.asp
  [29]: http://www.w3school.com.cn/cssref/selector_last-child.asp
  [30]: http://www.w3school.com.cn/cssref/selector_root.asp
  [31]: http://www.w3school.com.cn/cssref/selector_empty.asp
  [32]: http://www.w3school.com.cn/cssref/selector_target.asp
  [33]: http://www.w3school.com.cn/cssref/selector_enabled.asp
  [34]: http://www.w3school.com.cn/cssref/selector_disabled.asp
  [35]: http://www.w3school.com.cn/cssref/selector_checked.asp
  [36]: http://www.w3school.com.cn/cssref/selector_not.asp
  [37]: http://www.w3school.com.cn/cssref/selector_selection.asp
  [38]: http://www.w3school.com.cn/cssref/selector_element.asp
  [39]: http://www.w3school.com.cn/cssref/selector_element_comma.asp
  [40]: http://www.w3school.com.cn/cssref/selector_element_element.asp
  [41]: http://www.w3school.com.cn/cssref/selector_element_gt.asp
  [42]: http://www.w3school.com.cn/cssref/selector_element_gt.asp
  [43]: http://www.w3school.com.cn/cssref/selector_element_plus.asp
  [44]: http://www.w3school.com.cn/cssref/selector_all.asp
