## [display属性] 

- 描述：控制元素显示方式。
- 取值：`none`(不显示)、`block`(块显示)、`inline`(以行内元素显示)
- 注意：元素隐藏不再占空间了。



## [overflow属性]

- 描述：当内容溢出如何处理。
- 取值：scroll(出现滚动条)、hidden(隐藏)、auto(自动)、visible(显示)



```
.news{
	width:500px;
	height:300px;
	border:1px solid red;
	margin:50px auto;
	paddig:30px;
	overflow:scroll;
}
```

## [cursor光标类型]

- 描述：改变光标的显示类型。
- 取值：pointer(手形)、help(帮助)、text(文本)、wait(等待)等。

## [CSS定位属性]

1.`position`：定位属性，取值static、fixed、relative、absolute
`static`：静态定位，不定位，默认值。
`fixed`：固定定位。
`relative`：相对定位。相对所有标记的高度和
`absolute`：绝对定位。 相对的浏览器的边框

2.定位坐标值
`left`：距离目标元素左边的距离。
`right`：距离目标元素右边的距离。
`top`：距离目标元素顶边的距离
`bottom`：距离目标元素底边的距离。
提示：如果不指定定位坐标值，定位元素在“原地不动”。

3.固定定位——position:fixed
固定定位元素，是相对于浏览器窗口，来进行的定位。
固定定位元素，不再占空间了。
固定定位元素层级高于普通元素。
固定定位元素，一定是块元素，不管原来是什么元素。
如果不指定定位坐标，则该元素“原地不动”，位置不会改变。

```
.qq{
	width:100px;
	height:200px;
	background-color:green;
	position:fixed; /*固定定位*/
	right:200px;/*元素右边距离窗口右边距离*/
	top:200px;/*元素上边距离窗口上边距离*/
}
```

4.相对定位—— position:relative
相对定位，是相对于“原来的自己”进行的定位。
相对定位元素，所占的空间依然存在。
相对定位元素，层级要高于普通元素。
如果不指定定位坐标，该元素“原地不动”。
原来是什么元素，进行相对定位后，还是什么元素。
定位元素可以超出父元素的边界，而浮动元素，是不可以超出父元素的边界

## [HTML引入CSS的方法]

1.嵌入式
描述：通过`<style>`标记来书写CSS代码。
格式：`<style  type = “text/css”>……</style>`
说明：这种方式只能在当前HTML文件中使用，不能被多个HTML文件共享。
说明：`<style>`标记可以在网页中多次出现，想写在什么地方，就写在什么地方。

2.外联式
描述：将外部的 `.css`文件引入到当前的HTML文件中。
说明：可以将公共的CSS代码放在外部的文件，通过`<link>`标记将其引入，可以实现多个网页共享同一个CSS文件。
格式：`<link href = “css/public.css” type = “text/css” rel = “stylesheet” />`
属性：
`href`：指定外部的CSS文件路径。
`type`：指链入文件的类型。
`rel`：链接入文件与当前HTML文件的关系。取值：`stylesheet`。
说明：`<link>`标记是`<head>`的子标记。一个网页中也可出现多个`<link>`。`<link>`标记可以放在HTML网页的任何地方

3.行内式
描述：直接给HTML标记添加`style`属性。
每一个HTML标记，都有一些公共的属性：`id`、`class`、`style`、`title`等。
其中，`style`属性的值，就是CSS的代码。
行内样式的优先级最高。

### [CSS表格属性]

```
border-collapse`：合并表格边框线。取值：`collapse`(合并)
注意：不要再使用`rules`属性合并单元格边线了，因为兼容性不好。
```

<style type="text/css">
table{
	border:5px solid blue;
	border-collapse:collapse;
}
td{border:2px dotted red;}
</style>

## 全局CSS设置

1、所有HTML标记都要清除内外边距

```
html,body,ul,li,a,img,p,h1,h2,h3,h4,input{margin:0;padding:0;}

*{margin:0px;padding:0px;}
```

2、去除有序列列或无序列表前面的符号

```
ul,li,ol{list-style:none;}
```

3、网页中所有文字的大小及颜色

```
 body{ font-size:18px; color:#444; font-family:Arial , 楷体 , 宋体;}
```

4、去除图片的边框线

```
img{border:0;}
```

