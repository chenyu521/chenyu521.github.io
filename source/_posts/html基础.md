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
>
> <font color="red">
>
> <b>注意："mate charset="gbk"的作用是告诉浏览器采用哪一种字符集打开当前页面。并不是设置当前页面的字符编码格式"</b>
>
> </font>

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

# HTML的实体符号

|   符号   | 作用 |
| :------: | :--: |
|  `&lt;`  | 小于 |
|  `&gt;`  | 大于 |
| `&nbsp;` | 空格 |

```html
<!DOCTYPE html>
<html>
    <head>
        <title>实体符号</title>
    </head>
    <body>
        <!--实体符号特点是：以&开始，以;结束。&lt; 是小于号    &gt;是大于号    &nbsp;是空格-->
        b&lt;a&gt;c<br>
        a&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;b
    </body>
</html>
```

[点此预览](https://chenyu521-7g6cys1w453479b5-1257692848.tcloudbaseapp.com/3.html)

# HTML的表格

|   标签    |           作用           |
| :-------: | :----------------------: |
| `<table>` |           表格           |
|  `<tr>`   |        表格的一行        |
|  `<td>`   |          单元格          |
|  `<th>`   | 单元格（自动居中、加粗） |

表格的属性

| 标签                    | 作用       |
| ----------------------- | ---------- |
| align=center/left/right | 对齐方式   |
| width                   | 宽度       |
| height                  | 高度       |
| border                  | 表格框大小 |

```html
<!DOCTYPE html>
<html>
    <head>
        <title>表格</title>
    </head>
    <body>
        <!--
            border="1px"  设置表格的边框为1像素宽度。
            width 宽度
            height 高度
        -->
        <center><h1>测试表格</h1></center>
        <hr>
        <table align="center" border="1px" width="300px" height="150px">
            <!--align对齐方式-->
            <tr align="center">
                <td>a</td>
                <td>b</td>
                <td>c</td>
            </tr>
            <tr>
                <td>d</td>
                <td>e</td>
                <td>f</td>
            </tr>
            <tr>
                <td>x</td>
                <td>y</td>
                <td>z</td>
            </tr>
        </table>
    </body>
</html>
```

[点此预览](https://chenyu521-7g6cys1w453479b5-1257692848.tcloudbaseapp.com/4.html)

## HTML的单元格合并

> colspan 合并行
>
> rowspan 合并列

```html
<!DOCTYPE html>
<html>
    <head>
        <title>表格单元格合并</title>
    </head>
    <body>
        <!--
            1、row合并的时候，删除“下面的”单元格
            2、col合并的时候，对删除哪个没有要求
        -->
        <center><h1>测试表格</h1></center>
        <hr>
        <table align="center" border="1px" width="300px" height="150px">
            <tr>
                <!--th标签也是单元格标签，比td多的是居中，加粗-->
                <th>1</th>
                <th>2</th>
                <th>3</th>
            </tr>
            <tr>
                <td colspan="2">a</td>
                <!--
                <td>b</td>
                -->
                <td>c</td>
            </tr>
            <tr>
                <td>d</td>
                <td>e</td>
                <td rowspan="2">f</td>
            </tr>
            <tr>
                <td>x</td>
                <td>y</td>
                <!--
                <td>z</td>
                -->
            </tr>
        </table>
    </body>
</html>
```

[点此预览](https://chenyu521-7g6cys1w453479b5-1257692848.tcloudbaseapp.com/5.html)

## thead、tbody、tfoot标签

> 在table中不是必须的，只是便于后期的JS代码的编写
>
> thead:头
>
> tbody:体
>
> tfoot:脚

```html
<!DOCTYPE html>
<html>
    <head>
        <title>thead、tbody、tfoot标签</title>
    </head>
    <body>
        <center><h1>测试表格</h1></center>
        <hr >
        <table align="center" border="1px" width="300px" height="150px">
            <!--头部-->
            <thead>
                <tr>
                    <th>1</th>
                    <th>2</th>
                    <th>3</th>
                </tr>
            </thead>
            <!--体-->
            <tbody>
                <tr>
                    <td colspan="2">a</td>
                    <!--
                    <td>b</td>
                    -->
                    <td>c</td>
                </tr>
                <tr>
                    <td>d</td>
                    <td>e</td>
                    <td rowspan="2">f</td>
                </tr>
                <tr>
                    <td>x</td>
                    <td>y</td>
                    <!--
                    <td>z</td>
                    -->
                </tr>
            </tbody>
            <!--脚-->
            <tfoot>
                <tr>
                    <td>合计</td>
                    <td>1</td>
                    <td>2</td>
                </tr>
            </tfoot>
        </table>
    </body>
</html>
```

[点此预览](https://chenyu521-7g6cys1w453479b5-1257692848.tcloudbaseapp.com/6.html)

# 背景色和背景图片

| 属性名     | 作用     |
| ---------- | -------- |
| bgcolor    | 背景颜色 |
| background | 背景图片 |

```html
<!DOCTYPE html>
<html>
    <head>
        <title>背景颜色和背景图片</title>
    </head>
    <body bgcolor="red" background="img/play.png">
    </body>
</html>
```

[点此预览](https://chenyu521-7g6cys1w453479b5-1257692848.tcloudbaseapp.com/7.html)

# HTML图片img标签

| 属性         | 作用                     |
| ------------ | ------------------------ |
| img          | 图片标签                 |
| src          | 设置图片路径             |
| width/height | 图片的宽度/高度          |
| title        | 鼠标悬停时显示的信息     |
| alt          | 图片加载失败时显示的信息 |

```html
<!DOCTYPE html>
<html>
    <meta charset="utf-8">
    <head>
        <title>图片</title>
    </head>
    <body>
        <img src="img/play.png" width="100px" title="我是图片"/>
        <br><br>
        <img src="img/play1.png" alt="没有找到图片"/>
    </body>
</html>
```

[点此预览](https://chenyu521-7g6cys1w453479b5-1257692848.tcloudbaseapp.com/8.html)

# HTML超链接

> href:hot references热引用
>
> href属性后面一定是一个资源的地址
>
> href后面的路径可以是相对路径可以是绝对路径，也可以是网络上的地址
>
> 超链接的特点：有下划线；鼠标停留在超链接上面显示小手形状；点击超链接之后还能跳转页面
>
> 超链接的作用：通过超链接可以从浏览器向服务器发送请求，浏览器向服务器发送数据（请求：request）；服务器向浏览器发送数据（响应：response）
>
> B/S结构的系统，每一个请求都会对应一个响应。
>
> ​					B---------请求----------->   S
>
> ​					S---------响应------------>   B
>
> 用户点击超链接和用户在浏览器地址栏上输入URL，本质上没有区别，都是向服务器发送请求，从操作上来讲，超链接使用更方便
>
> 

超链接的target属性

| 属性    | 作用             |
| ------- | ---------------- |
| _blank  | 新窗口           |
| _self   | 当前窗口（默认） |
| _top    | 顶级窗口         |
| _parent | 父窗口           |

**`_blank`属性和`_self`属性可看后面例子的预览页面，至于父窗口以及顶级窗口具体可看网站右上角主页的导航站其中部分应用打开效果**

```html
<!DOCTYPE html>
<html>
    <meta charset="utf-8">
    <head>
        <title>超链接、热链接</title>
    </head>
    <body>
        <a href="https://www.baidu.com">百度</a>
        <br>
        <br>
        <!--
            href:hot references热引用
            href属性后面一定是一个资源的地址
            href后面的路径可以是相对路径可以是绝对路径，也可以是网络上的地址
        -->
        <a href="index.html">主页</a><br />
        <a href="https://www.baidu.com" target="_self">
            点击原窗口打开
            <img src="img/baidu.png" width="100px" />
        </a>

        <a href="https://www.baidu.com" target="_blank">
            点击新窗口打开
            <img src="img/baidu.png" width="100px" />
        </a>
    </body>
</html>
```

[点击预览](https://chenyu521-7g6cys1w453479b5-1257692848.tcloudbaseapp.com/9.html)

# HTML列表

有序列表的type属性：后面自定义

无序列表的type属性

| 属性   | 作用 |
| ------ | ---- |
| circle | 圈   |
| square | 方块 |
| disc   | 点   |

```html
<!DOCTYPE html>
<html>
    <meta charset="utf-8">
    <head>
        <title>HTML列表</title>
    </head>
    <body>
        <!--有序列表-->
        <ol>
            <li>水果</li>
            <li>蔬菜</li>
        </ol>
        <!--无序列表-->
        <ul>
            <li>中国</li>
                <ul>
                    <li>陕西</li>
                        <ul>
                            <li>西安</li>
                        </ul>
                    <li>北京</li>
                </ul>
            <li>美国</li>
            <li>英国</li>
        </ul>
    </body>
</html>
```

[点此预览](https://chenyu521-7g6cys1w453479b5-1257692848.tcloudbaseapp.com/10.html)

# HTML表单

## form表单初步

> 1、表单有什么用？
>
> - 手机用户信息，表单展现之后，用户填写表单，点击提交按钮提交数据给服务器
>
> 2、怎么画一个表单？
>
> - 使用form标签画表单
>
> 3、一个网页当中可以有多个表单
>
> 4、表单最终是需要提交数据给服务器的。form标签有一个action属性，这个属性用来指定服务器地址
>
> - action属性用来指定数据提交给哪个服务器。
> - action属性和超链接中的href属性一样，都可以给服务器发送请求（request）
>
> 5、 表单是以什么格式提交给服务器的？
>
> ​        https://localhost:8080/jd/login?username=abc&password=123
>
> ​        格式：action?name=value&name=value
>
> ​        HTTP协议规定的，必须以这种格式提交给服务器
>
> 6、form表单的method属性：
>
> - get：采用get方式提交的时候，用户提交的信息会显示在浏览器的地址栏上
> - post：采用post方式提交的时候，用户提交的信息不会显示在浏览器地址栏上
>
> 当用户提交的信息中含有敏感信息，例如：密码，建议采用post方式提交
>
> method的属性不指定，默认为get
>
> post提交的时候提交的数据格式和get还是一样的，只不过不在地址栏上显示出来
>
> 7、超链接也可以提交数据给服务器，但是提交的数据都是固定不变的，超链接是get请求，不是post请求
>
> <font color="red"><b>重点强调，表单项写了name属性的，一律会提交给服务器，不想提交就不写name<br />当name没有写的时候，该项不会提交给服务器<br />当value没有写的时候，value的默认值是空字符串""，会将空字符串提交给服务器</b></font>

input的type属性

| 属性            | 作用                                     |
| --------------- | ---------------------------------------- |
| text            | 文本框                                   |
| radio           | 单选框                                   |
| checkbox        | 复选框                                   |
| button          | 按钮                                     |
| sumbit（value） | 提交按钮(用于显示按钮上的文本信息)       |
| reset           | 重置按钮                                 |
| password        | 密码框                                   |
| select          | 下拉列表                                 |
| file            | 上传文件                                 |
| hidden          | 隐藏域（在网页上不显示，表单提交会提交） |

<font color="red"><b>注意事项：<br />单选按钮的value值必须手动指定<br />文本域没有value属性，用户填写的内容就是value</b></font>

```html
<!DOCTYPE html>
<html>
    <meta charset="utf-8">
    <head>
        <title>form表单</title>
    </head>
    <body>

        <!--画一个表单-->
        <form action="https://localhost:8080/oa/sava">
            <!--
                画一个提交按钮，这个按钮可以提交表单
                画按钮可以使用input输入域，type="submit"的时候表示该按钮是一个提交按钮，具有提交表单的功能
                对于按钮来说，按钮的value属性用来指定按钮上的文本信息
            -->
            <input type="submit" value="提交" />
            <!--这是一个普通按钮，不具备提交表单的功能-->
            <input type="button" value="文字啊" />
        </form>
        <!--这个按钮和普通的超链接没有什么太大的区别（超链接和表单都可以向服务器发送请求，只不过表单发送请求可以携带数据。）-->
        <form action="https://www.baidu.com/s">
            <input type="text" value="请输入你要百度的数据"  name="wd"/>
            <input type="submit" value="百度" />
        </form>

        <hr />
        <form action="https://localhost:8080/jd/login">
            用户名<input type="text" /><br />
            密码<input type="password" /><br />
            <input type="submit" value="登录" />
        </form>

        <!--
           
        -->

        <form action="https://localhost:8080/jd/login">
            <table>
                <tr>
                    <td>用户名</td>
                    <td><input type="text" name="username"/></td>
                </tr>
                <tr>
                    <td>密码</td>
                    <td><input type="password" name="password"/></td>
                </tr>
                <tr align="center">
                    <td colspan="2">
                        <input type="submit" value="登录" />
                        <!--submit和reset必须在标签内部-->
                        <input type="reset" value="清空" />
                    </td>
                </tr>
            </table>
        </form>
    </body>
</html>
```

[点此预览](https://chenyu521-7g6cys1w453479b5-1257692848.tcloudbaseapp.com/11.html)

## 用户注册的表单

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>用户注册的表单</title>
    </head>
    <body>
        <form action="https://localhost:8080/test" method="POST">
            用户名<input type="text" name="username" /><br />
            密码<input type="password" name="userpwd" /><br />
            确认密码<input type="password" /><br />
            性别
            <input type="radio" name="gender" value="1" checked />男
            <input type="radio" name="gender" value="0" />女
            兴趣爱好
            <input type="checkbox" name="interest" value="smoke" />抽烟
            <input type="checkbox" name="interest" value="drink" />喝酒
            <input type="checkbox" name="interest" value="sleep" />睡觉
            <br />
            学历
            <select name="grade">
                <option value="gz">高中</option>
                <option value="dz">大专</option>
                <option value="bk" selected>本科</option>
                <option value="ss">硕士</option>
            </select>
            简历
            <textarea rows="10" cols="60" name="introduce"></textarea>
            <input type="submit" value="提交" />
            <input type="reset" value="清空" />
        </form>
    </body>
</html>
```

[点此预览](https://chenyu521-7g6cys1w453479b5-1257692848.tcloudbaseapp.com/12.html)

## 下拉列表支持多选

> 使用`multiple="multiple"`使下拉列表支持多选，`size`设置显示的下拉列表数量，多选时按住`Ctrl`键再点击

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>下拉列表支持多选</title>
    </head>
    <body>
        <select multiple="multiple" size="2">
            <option>陕西省</option>
            <option>江西省</option>
            <option>山西省</option>
            <option>河北省</option>
        </select>
    </body>
</html>
```

[点此预览](https://chenyu521-7g6cys1w453479b5-1257692848.tcloudbaseapp.com/13.html)

## readonly和disabled

> readonly和disabled相同点，都是只读不能修改
>
> 但是readonly可以提交给服务器，disabled数据不会提交（即使有name属性也不会提交）

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>readonly和disabled</title>
    </head>
    <body>
        <form action="https://localhost:8080/test">
            用户代码<input type="text" name="usercode" value="1111" readonly /><br />
            用户名<input type="text" name="username" value="admin" disabled /><br />
            <input type="submit" value="提交" />
            
        </form>
    </body>
</html>
```

[点此预览](https://chenyu521-7g6cys1w453479b5-1257692848.tcloudbaseapp.com/14.html)

## 控件的maxlength属性

> maxlength是用来设置文本框中可输入的字符数量

# HTML中的id属性

> 在HTML文档中，任何元素（节点）都有id属性，id属性是该节点的唯一标识，所在在同一个html文档中id不能重复
>
> 注意：表单提交数据的时候，只和name有关系，和id无关
>
> id有什么用？
>
> Javascript语言可以对HTML文档中的任意节点进行增删改操作，增删改之前需要先拿到节点，通常我们通过id来获取节点对象
>
> id的存在让我们获取元素（节点）更方便
>
> HTML文档是一棵树，树上有很多节点，每一个节点都有一个唯一的id
>
> - JavaScript主要就是对这颗DOM树上的节点进行增删改的
> - DOM（Document）树。

# div和span在网页中的应用

> 1、div和span是什么？有什么用？
>
> - div和span都可以称为“图层”
> - 图层是作用是为了保证页面可以灵活的布局
> - 图层就是一个一个的盒子，div嵌套div就是盒子套盒子
> - div和span是可以定位的，只要定下div左上角的x轴和y轴即可
>
> 2、div和span区别？
>
> - div会独自占用一行，span不会

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>div和span</title>
    </head>
    <body>
        <div id="div1">我是一个div</div>
        <div id="div2">我是一个div</div>
        <span id="span1">我是一个span标签</span>
        <span id="span2">我是一个span标签</span>
        <div id="div3">
            <div>
                <div>test</div>
            </div>
        </div>
    </body>
</html>
```

[点此预览](https://chenyu521-7g6cys1w453479b5-1257692848.tcloudbaseapp.com/15.html)