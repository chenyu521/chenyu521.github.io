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

### 表格标记

- 作用：将数据更加有条理的显示出来，用来规划网页

- 语法：

  - `<table>`

    ​	`<tr>`

    ​			`<td>`单元格的内容`</td>`

    ​	`</tr>`

    `</table>`

    - tr：表示行（常用的属性 align 描述表格内的内容显示位置）
    - td：表示单元格，合并行：rowspan，合并单元格：colspan
    - th：表示单元格，自动居中、加粗。

  - 常用的属性

    - border：给表格添加边框
    - width：描述表格的宽度
    - align：描述表格的位置
    - cellspacing：描述边框的厚度
    - cellpadding：描述文字与边框的距离
    
  - 合并操作：

    - 要确定表格有多少行和多少列
    - 要确定合并的是行还是列

- 实例

```html
<html>
    <head>
		<title>Test3</title>
	</head>
	<body>
		<table border="1">
			<tr>
				<td>姓名</td>
				<td>语文</td>
				<td>数学</td>
				<td>英语</td>
			</tr>
			<tr>
				<td>小明</td>
				<td>90</td>
				<td>80</td>
				<td>85</td>
			</tr>
			<tr>
				<td>小花</td>
				<td>85</td>
				<td>80</td>
				<td>95</td>
			</tr>
		</table>
	</body>
</html>
```

### 表单标记

- 简介：把用户输入的数据提交到服务器端，简单来说，表单用来让用户输入数据，表单把数据封装起来，提交到指定的位置
- 表单组成：
  - 表单控件：用户输入数据，比如说输入用户名，输入密码
  - 提示信息：告诉用户输入框要输入什么值
  - 表单域：表示表单的开始和结束，语法`<form>`提示信息：表单控件`</form>`
- 创建表单

```html
<html>
	<head>
		<title>Test</title>
	</head>
	<body>
		<!-- 演示表单控件-->
		<fieldset>
			<legend>注册新用户</legend>
			<form action="#" method="POST">
				<table align="center" border="0" cellpadding="3">
					<tr>
						<!--文本框控件-->
						<td align="right">用户名：</td>
						<td>
							<input type="text" name="username" />
						</td>
					</tr>
					<tr>
						<!--密码控件-->
						<td align="right">密码：</td>
						<td>
							<input type="password" name="psw" />
						</td>
					</tr>
					<tr>
						<!--单选框控件-->
						<td align="right">性别：</td>
						<td>
							<input type="radio" name="sex" value="male" />男
							<input type="radio" name="sex" value="female" />女
						</td>
					</tr>
					<tr>
						<!--复选框控件-->
						<td align="right">兴趣爱好：</td>
						<td>
							<input type="checkbox" name="hobby" value="film" />看电影
							<input type="checkbox" name="hobby" value="code" />编程
							<input type="checkbox" name="hobby" value="game" />打游戏
						</td>
					</tr>
					<tr>
						<!--文件上传控件-->
						<td align="right">头像：</td>
						<td>
							<input type="file" name="photo" />
						</td>
					</tr>
					<tr>
						<!--按钮控件-->
						<td align="center" colspan="2">
							<input type="submit" value="注册" />
							<input type="reset" value="重置" />
						</td>
					</tr>
                    
				</table>
			</form>
		</fieldset>
	</body>
</html>
```

- 常用的属性：

  - action：表示表单要提交的位置
  - method：表单提交的方式，常用的有get提交和post提交，默认提交方式是get
  - get提交：数据会显示在浏览器的地址栏，不安全，提交的数据大小有限制
  - post提交：数据不会显示在地址栏，是安全的，提交的数据大小没有限制

- 表单控件：`<input />`

  - 输入框控件的属性type：

    - 文本框：text
    - 密码框：password
    - 单选按钮：radio
    - 复选按钮：checkout
    - 上传控件：file
    - 提交按钮：submit
    - 重置按钮：reset

    注意：表单想要把数据提交到指定的位置，输入框必须要有name属性。

- 文本域标记：`<textarea rows="文本域的行数" cols="文本域每行输入的字符数"></textarea>`

  ```html
  <html>
  	<head>
  		<title>Test</title>
  	</head>
  	<body>
  		<form action="#" method="GET">
  			<textarea rows="5" cols="50" name="pinglun">输入评论</textarea><br />
  			<input type="submit" value="提交评论" />
  		</form>
  	</body>
  </html>
  ```

  

