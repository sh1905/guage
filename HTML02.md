# HTML Lesson 1

## 1.[初始HTML]

### 1.1 html文件结构

#### HTML结构树

![](C:\Users\联想\Desktop\Python\第二阶段：HTML5\web_1\images_1\tree.png)

#### 结构

<!DOCTYPE html>   #  不是html标签，告知浏览器页面使用的是html什么版本。
<html>            #  html标签
<head>            #  HTML的头部标签
<meta charset= "utf-8" />   #  设置字符集
    <title>网页的标题</title>   #  设置字符集
    </head>

    <body>   #  网页的正文内容
        body中的网页的正文内容
    </body>
    </html>


<html></html>:表示一个网页，或者告诉浏览器是什么类型的文件。
<html>有两个子标记<head>和<body>。
    <head></head>:称为文件头标记，内容一半是控制信息，信息是浏览器中看不见的。
    <title></title>:表示网页的标题，其内容只能是纯文本。
    <meta />标记，告诉浏览器，这个网页中的汉字用UTF-8编码解析。

### 1.2 html标签格式

HTML标签分两类：一是双边标记（常规标签），二是单边标记（空标签）。

格式一：<标签  属性 = “属性值”  属性 = “属性值”>内容</标签>

<font color='red'  face='楷体' size='6'>中国上海</font>

格式二：<标签  属性 = “属性值”  />



### 1.3 对属性的理解

HTML标记不区分大小写；

标记可能有属性，可能没属性；

各属性之间用空格隔开；

只能顺序嵌套，不能交叉嵌套。





## 2.[HTML]文本修饰标记

#### 2.1 各种主要功能

<b></b>    文本加粗

<i></i>    文本斜体

<u></u>    下划线

<s></s>    删除线

<sup></sup>   上标

<sub></sub>   下标

<font></font>   文本字体



其中font又包含其他属性，如文本颜色。

文本大小：取值1-7；

字体样式：取值黑体，楷体......



## 2.[HTML排版标记]

#### 1,<p>段落

格式：<p>........</p>

常用属性：

align：文本的水平对齐方式，取值：left(左)，center(中)，right（友）

特点：在段前或段后，会有一个空行。



如：<p align='center'>我在中间</p>



#### 2,换行标记<br />

换段标记，在段落前后会多一个空行。

换行标记，行间距不会发生任何改变。



#### 3,水平线标记<hr   /r>

语法： <hr 属性=“属性值”/>

属性：

color：线条颜色

size：线的粗细

width：线的宽度

align：线的水平对齐方式

noshade：是否要去掉阴影，该属性没有值。

<hr noshade size='1'/>
#### 4,预排版标记：<pre></pre>

描述：可以保留所有的空白字符（换行，空行，空格）。

语法：<pre  属性 = “属性值”>......</pre>

属性：width,元素的宽度。



#### 5，标题标记<h1>...<h1>

描述：一共有六个标题标记，分别为<h1>,<h2>,<h3><h4>,<h5>,<h6>其中<h1>最大，<h6>最小。

语法：`<h1 属性 = “属性值”>`……</h1>

属性：`align`，水平对齐方式，取值：`left、center、right`

<h1 align='center'><font color='red'>中国上海</font></h1>


## 3.[块元素和行内元素（div和span）]

#### 1,块元素

特点：块元素的宽度`撑满整个网页`(父元素)。

块元素一定要`另起一行`进行排版。

块元素`单独占一行`，不管有多少内容。

常用的块元素:`<p>、<h1>、<h2>、<h3>、<pre>、<div>、<table>`......



#### 2,行内元素

特点：行内元素`没有宽度`，行内元素的宽度主要由`内容`决定。

行内元素`不会另起一行`排版。

多个行内元素排在同一行。

常用的行内元素有哪些？`<font>、<b>、<i>、<u>、<sup>、<sub>、<span>`等

注意事项：行内元素和块元素，`相互嵌套时，块元素中嵌套行内元素`。



## 4.[HTML中的列表--块元素]

#### 1.html项目符号(无序列表)

```
<ul>
	<li>内容</li>
	<li>内容</li>
	<li>内容</li>
	<li>内容</li>
	<li>内容</li>
</ul>
```

`<ul>`和`<li>`的公共属性

type`：项目符号的类型，取值：`disc`(小黑点)、`circle`(圆圈)、`square`(小方块)

```
<ul type='square'>
	<li>内容</li>
	<li type='disc'>内容</li>
	<li>内容</li>
	<li type='circle'>内容</li>
	<li>内容</li>
</ul>
```

<ul type='square'>
	<li>内容</li>
	<li type='disc'>内容</li>
	<li>内容</li>
	<li type='circle'>内容</li>
	<li>内容</li>
</ul>

标记嵌套的原则：一定是在`最底层标记中`，来嵌套一个完整的其它标记。

```
<h1>省份城市列表<h1>
<ul>
	<li>安徽
		<ul>
			<li>合肥</li>
			<li>芜湖</li>
			<li>黄山</li>
		</ul>
	</li>
	<li>江苏
		<ul>
			<li>苏州</li>
			<li>无锡</li>
			<li>常州</li>
		</ul>
	</li>
</ul>
```



#### 2.html编号列表(有序列表)

```
<ol>
	<li>内容</li>
	<li>内容</li>
	<li>内容</li>
	<li>内容</li>
	<li>内容</li>
</ol>
```



`<ol>`和`<li>`的公共属性

type：编号的类型。取值：a、A、1、i、I

start：从第几个开始。该值一定是正整数。

```
<h1>省份城市列表<h1>
<ol>
	<li>安徽
		<ol type='a' start='2'>
			<li>合肥</li>
			<li>芜湖</li>
			<li>黄山</li>
		</ol>
	</li>
	<li>江苏
		<ol type='I' start='2'>
			<li>苏州</li>
			<li>无锡</li>
			<li>常州</li>
		</ol>
	</li>
</ol>
```





#### 3.html自定义列表

```
<dl>
	<dt>标题1</dt>
	<dd>内容1</dd>
	<dt>标题2</dt>
	<dd>内容2</dd>
</dl>
```

<dl>
	<dt>标题1</dt>
	<dd>内容1</dd>
	<dt>标题2</dt>
	<dd>内容2</dd>
</dl>

`<dl>` 标签用于结合 `<dt>` （定义列表中的项目）和 `<dd>` （描述列表中的项目）。

```
<dl>
	<dt>省份</dt>
		<dd>上海</dd>
		<dd>福建</dd>
		<dd>浙江</dd>
	<dt>货币</dt>
		<dd>人民币</dd>
		<dd>美元</dd>
		<dd>英镑</dd>
</dl>
```

<dl>
	<dt>省份</dt>
		<dd>上海</dd>
		<dd>福建</dd>
		<dd>浙江</dd>
	<dt>货币</dt>
		<dd>人民币</dd>
		<dd>美元</dd>
		<dd>英镑</dd>
</dl>



## 5.[滚动字幕标记]

语法：`<marquee 属性 = “属性值”>……</marquee>`

属性:

```
Direction：滚动的方向，取值：left、right、up、down
Width：宽度
Height：高度
bgColor：背景色
scrollAmount：滚动步长值。值越大滚动的越快。默认值为6px。
scrollDelay：延时时间，两步之间停留的时间，以毫秒为单位。1秒＝1000毫秒
```

```
<marquee direction='left' width='400px' height='300px' bgcolor='#ffff66' scrollAmount='100' scrollDelay='40'>
<p>我是漂浮物</p>
</marquee>
```

# HTML Lesson 2

## [图片标记——行内元素]

语法格式:`<img  属性 = “属性值” />`
常用属性:

src：指图片的路径，该路径可以是相对地址，也可以是绝对地址。
width：图片的宽度。
height：图片的高度。
alt：图片说明。当图片不存在时，显示一个提示信息。
border：图片边框的粗细。
left或right：可以实现图文混排。
left或right的功能相当于CSS中的“浮动”效果。

## 超级链接——行内元素

语法格式：`<a  属性 = “属性值”>……</a>`
常用属性:

href：链接的地址。该地址可以是绝对路径，也可以是相对路径。
target：链接的目标文件在哪个窗口中来打开。
		_blank：弹出一个空白窗口来打开文件。
		_self：在当前窗口中来打开目标文件。
		_parent：在父窗口中来打开目标文件。(常用于框架网页中)
		_top：在最顶层窗口中来打开目标文件。(常用于框架网页中)
name：指定一个锚点名称。所谓“锚点”用于长网页当中。

2、相对路径

（1）当前文件和目标文件在同一个目录下
如果当前文件和目标文件在同一个目录下，是同一级情况下，链接地址：`直接写目标文件名即可`。

（2）当前文件和目标文件所在的目录是同一级
链接地址：`先写目标文件夹名，再写目标文件名`。

3）目标文件位于上级目录中
链接地址：`先向上走一级(../)，再往上走一级(../../)，再找某个文件夹，再找文件夹下的文件`。

## ##[锚点链接]

锚点链接：可以实现在一个网页的不同部分实现跳转，用在长网页当中(`一定要有滚动条`)。锚点可以理解为一个`记号`。
锚点的制作两个步骤。
定义锚点(记号):`<a  name = “top”></a>`
锚点的命名规则:

名称可以包含 a-z、A-Z、0-9、_这些符号。
不能以数字开头。
可以以字母或下划线开头。

跳转到锚点(记号)：省略文件名：<a  href = “#top">返回顶部</a>
不省略文件名：<a  href = “index.html#top">返回顶部</a>
文件名可以省略。如果省略，跳转到当前网页的那个记号处。

## [表格标签]

1.表格的结构：<table>`代表表格标记。`<tr>`代表行标记。`<td>`普通单元格。
`<td>`可以理解为X轴,也就是一列;`<tr>`可以理解为Y轴,也就是一行;

2.table属性：

border：边线粗细。
bordercolor：边线颜色。
width：表格宽度。
height：表格高度。
align：水平对齐方式，取值：left、center、right
bgColor：背景颜色
background：背景图片
rules：合并所有单元格边线。取值：all
cellpadding：内填充距离(单元格边线到内容间的距离)
cellspacing：单元格间距(两个单元格边线之间的距离)

3.tr属性：

height：行高。
bgColor：背景色
background：背景图片
align：水平对齐方式，取值：left、center、right
valign：垂直对齐方式，取值：top、middle、bottom

4.td或th属性：

width：单元格宽度。
height：单元格高度。
bgColor：背景色
background：背景图片
align：水平对齐方式
valign：垂直对齐方式
colspan：合并列的单元格。
rowspan：合并行的单元格。

5.caption表格标题：

含义：给表格添加一个标题。
语法：<caption>……</caption>
说明：<caption>标记，放在<table>开始标记之后，所有的<tr>标记之前。一个表格只能有一个<caption>标记。

有一个库，html库

import html

print(html.escape('div'))



