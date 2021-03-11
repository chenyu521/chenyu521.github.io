---
title: JavaScript笔记
date: 2021-03-11 18:46:48
tags:
	- 教程
	- 笔记
	- JavaScript
cate:
	- 教程
	- JavaScript
---

# 第一章：Html技术、CSS技术、JavaScript技术

## Html技术

### Html简介

- 它是一门描述网页的语言，HyperText MarkUp Language，超文本标记语言。

  - 超文本：超出文本的范畴，指的在网页上面可以描述文本、图片、视频等内容
  - 标记：标签，在标签里面书写内容
  - 语言：html就是用户和浏览器交互的工具，简单来讲，浏览器会解析html的标记，以特定的效果给展示出来

- html的主要组成部分：

  - 文档的声明<!DOCTYPE>：声明了html的类型和版本号
  - html的根标记`<html>` `</html>`：标识html的开始和结束
  - html的头部标记`<head>` `</head>`：设置页面相关信息
  - html的主体标记`<body>`  `</body>`：在页面展示内容

- html的书写规范：

  - html的文件后缀名可以是"`.html`"或者"`.htm`".
  - html文件的格式：

  ```html
  <html>
  	<head>
  		<title>Test</title>
  	</head>
  	<body>
  		This is my first html page.
  	</body>
  </html>
  ```

  - html文件必须以`<html>`开始，以`</html>`结束
  - html语法不区分大小写
  - html有结束标记，比如`<font>`内容`</font>`，html的标记如果没有结束标记，自己结束。比如`<hr />`

- html作用：它用来编写网页，在网页通过html标记来描述文本、图片、视频等内容

### 单标记和双标记

- 单标记：空标记，就是没有结束标记的称之为单标记。
  - 语法：`<hr />`   `<br />`
- 双标记：体标记，就是这个标记有开始和结束。
  - 语法：`<font>`内容`</font>`

### 文本控制和文本样式标记

- 段落标记`<p>`   `</p>`和换行标记`<br />`

  - 段落标记：段落与段落之间会自动换行。

  ```html
  <html>
     	<head>
  		<title>Test2</title>
  	</head>
  	<body>
  		<p>我是谁</p>
  		<p>我来自哪里</p>
  		<hr />
  		<p>使用html制作网页时可以通过br标记<br />实现换行效果</p>
  	</body>
  </html>
  ```

- 文本样式标记`<font>`内容`</font>`

  - 常用的属性：
    - face用来描述字体的样式
    - size用来描述字体的大小，最大取值为7
    - color用来描述字体的颜色，有三种形式表示（英文单词（red）、16进制（#ff0000）、rgb(255,255,0)）

    ```html
    <html>
        <head>
    		<title>Test3</title>
    	</head>
    	<body>
    		我是默认的文本<br />
    		<font face="微软雅黑" size="7" color="green">我是7号绿色文本，我的字体是微软雅黑</font>
    	</body>
    </html>
    ```

- 其他标记

  - 标题标记：`<h1>` `</h1>`······`<h6>` `</h6>`
  - 字体样式标记：`<b>` `</b>`；`<u>` `</u>`；`<i>` `</i>`

### 图像标记

- 作用：在网页上引入图片

  - 语法：`<img src="image url" />`

  - 常用属性：

    - src用来引入图片
    - width描述图片的宽度
    - height描述图片的边框
    - border用来描述图片的边框

    注意：图片的路劲分为绝对路径和相对路径（同级目录，上级目录，下级目录）

  - 注释标记：`<!--文字内容-->`，注释标记的内容不会显示在网页上面