# 借助小可嗒嗒的模板建起的个人博客，详细介绍见下方：
# 关于这个Jekyll模板主题 ⚽⚽⚽

## 预览

### 首页



+ 首页: 博客首页
+ 博文分类: 按照categories对文章进行分类
+ 标签分类: 按照tags对文章进行分类
+ 外域链接: 存放一些想要其他网站的链接
+ DEMO: 存放个人项目
+ 打赏我: 提供donation
+ 关于我: 个人CV



## 功能简介

### 提供全文搜索

博客使用[`Simple-Jekyll-Search`](https://github.com/christian-fei/Simple-Jekyll-Search)提供全文搜索功能。

相关介绍和操作可参考: [加入搜索功能](http://xiaokedada.com/2017/05/09/Jekyll-second/#加入搜索功能)




### 使用canvas实现首页动态效果

### 使用日历控件显示当前日期

[在线演示](http://xiaokedada.com/effects/demo/demo-calender/index.html)

### 使用tagCloud控件实现云标签效果

[在线演示](http://xiaokedada.com/effects/demo/demo-tagscloud/index.html)

---

## 博客使用方法

初识Jekyll博客，有必要了解[Jekyll](https://jekyllrb.com/)有关知识。

相关的内容我写了两篇文章可供参考

+ [基于Jekyll静态框架的Github站点设计](http://xiaokedada.com/2017/02/22/Jekyll-Cpanel/)
+ [Jekyll搭建博客--人类补完计划](http://xiaokedada.com/2017/05/09/Jekyll-second/)

### 部署和安装

请参考[Jekyll相关](http://xiaokedada.com/2017/02/22/Jekyll-Cpanel/#jekyll相关)。


### 修改_config.yml文件

包括相关的一些设置参数，包括banner/motto/description等。

> 直接修改便会生效。

### 写文章

文章放在`_post`文件夹下，可创建自命名文件夹。支持markdown编写，提供`post`(知识共享署名-非商业性使用-禁止演绎 4.0 国际许可协议)/`original`(原创文章)两种方式。

文件命名示例如下:

```
2017-03-23-More-of-prototype.md
```

文章首部字段为:

```markdown
---
layout: post
title: "再谈原型和继承"
date: 2017-03-23 09:00:00 +0800
categories: 研究生涯
tag: JavaScript
---
* content
{:toc}
```

多tag可参考文章:[加入多个标签](http://xiaokedada.com/2017/05/09/Jekyll-second/#如何加入多个标签)

> 备注一: Jekyll使用时间对文章进行排序，所以无论如何建立文件夹和文件夹命名都行，你开心就好

> 备注二: 未完成的草稿文章可以放在`_draft`文件夹中

### 运行

使用下面命令可直接运行:

```bash
$ jekyll s
```

会开启jekyll服务器，监听在`http://127.0.0.1:4000/`，使用浏览器访问呢。

不想查看效果，可直接bulid。

```bash
$ jekyll build
```

> 备注: 草稿区的内容不会显示，如果想要对草稿去内容进行查看，可参考[开启草稿](http://xiaokedada.com/2017/05/09/Jekyll-second/#jekyll的一些使用技巧)



---

## Update Log

### 2017.07.16

- [-] 删除网易云跟帖
- [+] 将网易云跟帖更改为gitment
- [+] 添加一个新模块: TalkToMe

### 2017.06.17

- [^] 改变文章字体
- [+] 增加不蒜子
- [^] 将多说更改为网易云跟帖
- [+] 添加搜索功能
- [^] 代码高亮改为rouge


### 2017.04.20

- [+] First commit
- [+] 添加首页Canvas效果
- [+] 添加日历控件
- [+] 添加云标签控件
- [+] 添加社会化评论多说
- [+] 大量优化
- [+] 添加favicon.ico

