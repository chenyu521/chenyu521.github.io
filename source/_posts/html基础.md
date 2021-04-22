---
title: html基础
date: 2021-03-26 17:09:09
tags:
	- Html
	- 笔记
categories:
	- 教程
	- Html
---

 1、系统结构：

- B/S架构：Browser/Server（浏览器/服务器的交互形式）
  - Browser支持的语言：HTML、CSS、JavaScript
  - Server端的语言：C、C++、Java、Python......
  - B/S架构的系统有什么优点和缺点：
    - 优点：升级方便，只升级服务器端代码即可。维护成本低
    - 缺点：速度慢、体验不好
- C/S架构：Client/Server（客户端/服务器端的交互形式）
  - C/S架构的系统有什么优点和缺点：
    - 优点：速度快，体验好。（娱乐型的系统多数是C/S架构）
    - 缺点：升级麻烦，维护成本较高

2、什么是HTML？怎么开发HTMl？怎么运行HTML？

> HTML:Hyper Text Markup Language(超文本标记语言)

由大量的标签组成，每一个标签都有开始标签和结束标签。

<标签>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<标签>

​		&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<标签 属性名="属性值" 属性名=“属性值”>

​	&nbsp;&nbsp;&nbsp;&nbsp;<标签>

<标签>

超文本：流媒体、图片、声音、视频......

HTML开发的时候使用普通的文本编辑器就行，创建的文件扩展名是`.html`或者`.htm`

HTML也有专业的开发工具，例如：DreamWeaver、HBuilder......

直接采用浏览器打开HTMl文件就是运行。

3、HTML是谁制定的？

W3C：世界万维网联盟

W3C制定了HTML的规范，每个浏览器生产厂家都会遵守规范。HTML程序员也会按照这个规范去写代码。

W3C制定了很多规范：

​	HTML/XML/http协议/https协议......

# 我的第一个HTML

```html
<!-- 
    1、这是HTML的注释
    2、加上以下代码的第一行就表示HTML5语法。去掉就表示HTML4.0
    3、HTML不区分大小写，语法松散不严格。
-->

<!DOCTYPE html>
<!-- 根-->
<html>
    <!-- 头-->
	<head>
        <!-- 网页标题，显示在网页左上角-->
		<title>网页的标题</title>
	</head>
    <!--网页主体-->
	<body>
		网页的主体内容
	</body>
</html>
```

[点击此处预览](https://chenyu521-7g6cys1w453479b5-1257692848.tcloudbaseapp.com/1.html)

# HTML的基本标签

| 标签     | 介绍     |
| -------- | -------- |
| `<p>`    | 段落标记 |
| `<h1>`   | 标题字   |
| `<br>`   | 换行标记 |
| `<hr>`   | 水平线   |
| `<pre>`  | 预留格式 |
| `<del>`  | 删除字   |
| `<ins>`  | 插入字   |
| `<b>`    | 粗体字   |
| `<i>`    | 斜体字   |
| `<sup>`  | 上标     |
| `<sub>`  | 下标     |
| `<font>` | 字体标签 |



```html
<!DOCTYPE html>
<html>
    <head>
        <title>HTML的基本标签</title>
    </head>
    <body>
        <!--段落标记-->
        <p>第一段</p>
        <p>第二段</p>
        <!--标题字：是HTML预留的格式-->
        <h1>一级标题</h1>
        <h2>二级标题</h2>
        <h3>三级标题</h3>
        <h4>四级标题</h4>
        <h5>五级标题</h5>
        <h6>六级标题</h6>
        <!--换行标记，<br>是一个独目标记-->
        从此处<br>换行
        <!--水平线，独目标记-->
        <hr>
        <!--color和width都是hr标签的属性-->
        <hr color="red" width="50%">
        <!--预留格式-->
        <pre>
            for(int i = 0; i < 10; i++){
                System.out.println("i = " + i);
            }
        </pre>

        <del>删除字</del>
        <ins>插入字</ins>
        <b>粗体字</b>
        <i>斜体字</i>

        <!--上标-->
        10<sup>2</sup>
        <!--下标-->
        10<sub>m</sub>

        <!--字体标签-->
        <font color="red" size="50">字体标签</font>
    </body>
</html>
```

[点击此处预览](https://chenyu521-7g6cys1w453479b5-1257692848.tcloudbaseapp.com/2.html)