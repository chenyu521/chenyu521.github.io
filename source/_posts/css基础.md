---
title: css基础
date: 2021-04-23 19:15:21
tags:
---

# CSS概述

> 什么是CSS，有什么用？
>
> - CSS（Cascading Style Sheet）：层叠样式表语言。
> - CSS的作用是：
>   - 修饰HTML页面，设置HTML页面中的某些元素的样式，让HTML页面更好看。
>   - CSS好比是HTML的化妆品一样。
> - HTML还是主体，CSS依赖HTML。CSS的存在就是修饰HTML，所以新建的文件还是xx.html文件。

# HTML引入CSS样式的三种方法概述

> 第一种方式：在标签内部使用style属性来设置元素的CSS样式，这种方式称为内联定义方式。
>
> - 语法格式
>   - <标签    style="样式名：样式值；样式名：样式值；...."></标签>
>
> 第二种方式：在head标签中使用style块，这种方式被称为样式块方式。
>
> - 语法格式
>
>   - ```html
>     <head>
>         <style type="text/css">
>             选择器{
>                 样式名：样式值；
>                 样式名：样式值；
>                 ······
>             }
>             选择题{
>                 样式名：样式值；
>                 样式名：样式值；
>                 ······
>             }
>         </style>
>     </head>
>     ```
>
> 第三种方式：链入外部样式表文件，这种方式最常用。（将样式写到一个独立的xxx.css文件当中，在需要的网页上直接引入css文件，样式就引入了）
>
> - 语法格式
>
>   - ```html
>     <link type="text/css" rel="stylesheet" href="css文件的路径" />
>     ```
>
> - 这种方式易维护，维护成本较低。

# 内联定义方式

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>HTML中引入CSS样式的第一种方式：内联定义方式</title>
    </head>
    <body>
        <div style="width: 300px; height: 300px; background-color: yellowgreen; display: block; border-color: red; border-width: 1px; border-style: solid;"></div>
        <br />
        <div style="width: 300px; height: 300px; background-color: aqua; display: block; border: 1px solid black;"></div>
    </body>
</html>
```

[点此预览](https://chenyu521-7g6cys1w453479b5-1257692848.tcloudbaseapp.com/16.html)

## id选择器、标签选择器和类选择器

id选择器的示例

```html
<style>
	#id名{
    	样式名：样式值；
    	样式名：样式值；
    	样式名：样式值；
        ·······
	}
</style>
```

标签选择器的示例（标签选择器作用比id选择器广）

```html
<style>
    标签名{
    	样式名：样式值；
    	样式名：样式值；
    	样式名：样式值；
        ······
    }
</style>
```

类选择器的示例

```html
<style>
    .类名{
        样式名：样式值；
        样式名：样式值；
        样式名：样式值；
        ······
    }
</style>
```



# 样式块

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>HTML中引入CSS样式的第二种方式：样式块</title>
        <style>
            /*id选择器*/
            #usernameErrorMsg{
                color: red;
                font-size: 12px;
            }
            /*标签选择器*/
            div {
                background-color: brown;
                border: 1px solid yellow;
                width: 100px;
                height: 100px;
            }
            /*类选择题*/
            .myclass{
                border: 1px solid red;
                width: 400px;
                height: 30px;
            }
        </style>
    </head>
    <body>
        <span id="usernameErrorMsg">对不起，用户名不能为空！</span>
        <br /><br /><br /><br />
        <div></div>
        <div></div>
        <div></div>
        <br /><br /><br /><br />
        <input type="text" class="myclass" />
        <br /><br /><br /><br /><br />
        <select class="myclass">
            <option>专科</option>
            <option>本科</option>
        </select>
    </body>
</html>
```

[点此预览](https://chenyu521-7g6cys1w453479b5-1257692848.tcloudbaseapp.com/17.html)

# 链入外部样式表

css文件

```css
a{
    text-decoration: none;
}
#wu{
    text-decoration: underline;
    cursor: pointer;
}
```

html文件

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <link type="text/css" rel="stylesheet" href="css/1.css" />
        <title>HTML中引入CSS样式的第三种方式：链入外部样式表</title>
    </head>
    <body>
        <a href="https://www.baidu.com">百度</a>
        <span id="wu">点我</span>
    </body>
</html>
```

[点此预览](https://chenyu521-7g6cys1w453479b5-1257692848.tcloudbaseapp.com/18.html)

# 列表样式

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>列表样式</title>
        <style>
            ul{
                list-style-type: none;
            }
        </style>
    </head>
    <body>
        <ul>
            <li>中国
                <ul>
                    <li>陕西</li>
                    <li>北京</li>
                    <li>山西</li>
                </ul>
            </li>
            <li>美国</li>
        </ul>
    </body>
</html>
```

[点此预览](https://chenyu521-7g6cys1w453479b5-1257692848.tcloudbaseapp.com/19.html)

# 绝对定位

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>绝对定位</title>
        <style>
            #div1{
                background-color: red;
                border: 1px solid black;
                width: 300px;
                height: 300px;
                position: absolute;
                left: 100px;
                top: 100px;
            }
        </style>
    </head>
    <body>
        <div id="div1"></div>
    </body>
</html>
```

[点此预览](https://chenyu521-7g6cys1w453479b5-1257692848.tcloudbaseapp.com/20.html)