---
layout: post
title: "特指度--确定哪个样式胜出"
date: 2017-05-16 09:00:00 +0800 
categories: rwd
tag: CSS
permalink: /posts/rwd/特指度--确定哪个样式胜出
---
* content
{:toc}

有些`CSS`属性有些是可以继承的，有些是不可以继承的。在多个规则定义了相同的`CSS`属性，并且这些规则都应用在页面的同一元素上，有时候，会产生冲突。对于现代浏览器，有一种`cascade`的机制，用来进行冲突判定。

有两种情况会导致样式冲突：

+ 继承，从多个祖辈那里继承相同的属性，针对标签样式的继承
+ 同一个元素有多个样式。比如说，我们为一个段落定义了`Class`样式，又定义了`<p>`标签样式

<!-- more -->

## 对第一种冲突的处理方法

对于第一种冲突，我们来举一个例子。我们将`<body>`标签的文字设为红色，把`<p>`标签的文字颜色设为绿色。同时，段落中有一个`<strong>`标签，这个标签里的文字会怎么显示呢？

```css
body {
    font-family: Arial, Helvetica, sans-serif;
    color: red;
}
p {
    color: green;
}
```

### 最近的祖辈胜出

浏览器对这种冲突的处理方法是，如果没有专门为标签定义样式，继承的属性出现冲突时，**最近的祖辈胜出**。

### 直接应用在标签上的样式胜出

标签专用样式里的属性会击败所有继承的属性。

---

## 一个标签，多个样式

这就是我们处理的第二种冲突，有下面几种可能会产生冲突的几种情况：

+ 类型选择器(也就是标签选择器)定义了样式，又有类或者`id`样式应用到标签上
+ 相同的样式名在样式表中出现多次。比如，群组选择符`.leadHeadline, .secondaryHeadline, .newsHeadline`，还有一个类样式`.leadHeadline`
+ 既有类样式，又有`id`样式的标签
+ 一个网页用到了多个样式表，有些是外部样式表(比如自定义的`styles.css`文件)，有些是内部样式表(应用在`html`文件内部)，还有些是链接的外部样式表(比如：`Bootstrap`)，各个样式表中都有名称相同的样式
+ 多个复杂的选择器选取相同的标签

### 特指度

+ 一个标签选择器记**1分**，伪元素(如`::first-line`)与标签一样，记为**1分**
+ 一个类选择器记**10分**，伪类(如`:link`)与类选择器一样，记为**10分**
+ 一个`id`选择器记**100分**
+ 一个行内样式记为**1000分**
+ 后代选择器的特指度是其中各个选择器的得分总和

所以，解决方案是： **特指度高的胜出**。

如果特指度相同，则**后一个样式胜出**。

### 忽略特指度

只需要在某个属性后边加上`!important`。

### 避免特指度战争

为了让某个样式胜出，我们的选择符也许会像裹脚布一样又长又臭。这是应该避免的。

---

## CSS Reset

为了剔除浏览器内置的一些属性，我们可以使用一些`CSS`重置代码。

在这中，`normalize.css`就是个不错的重置方案。

---

## 实战案例：覆盖Bootstrap的样式

有时候，我们的网站会引入`Bootstrap.css`文件，有时候我们需要用自己的样式表对某个标签进行修改，有什么办法呢？

+ `Bootstrap.css`文件在前面加载。这就是利用特指度相同，**后一个样式胜出**
+ 增加特指度
+ 粗暴加入`!important`
