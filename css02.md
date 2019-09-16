## [CSS列表属性]

列表属性样式如下：

```
.ul{list-style:none;}
```

## [CSS边框属性]

```
border-right：右边框线。
border-top：上边框线。
border-bottom：下边框
简写方式：
	border：四个边框都加同一种边线。
	举例：div{border:2px solid blue;}
```

## [CSS填充属性]

### 一.内边距-边线到内容间的距离

```
简写方式:
	padding:10px; //四个内填充都是10px
	padding:10px 20px; //上下内填充为10px，左右内填充为20px
	padding:5px 10px 15px; //上填充为5px，左右为10px，下为15px
	padding:5px 10px 15px 20px;  //顺序一定为：上右下左
```

### 二.外边距：边框线往外的距离

```
简写方式:
	margin:10px;   //四个外边距分别为10px
	margin:10px 20px;  //上下外边距10px，左右外边距20px
	margin:5px 10px 15px;  //上外边距5px，左右外边距10px，下外边距15px
	margin:5px 10px 15px 20px;  //顺序一定是：上右下左
```

## [CSS背景属性]

```
background-color：背景颜色
background-image：图片的路径(相对路径或绝对路径)。如：background-image:url(images/bg.gif);
background-repeat：控制图片的平铺方式。
	no-repeat：不平铺。
	repeat-x：水平方向平铺。
	repeat-y：垂直方向平铺。
repeat：水平和垂直都平铺(默认)。
```

## [CSS浮动和清除]

### 1.CSS浮动(飘起来)

- float：浮动属性，取值：left或right。

- CSS浮动可以使元素向左或向右浮动。浮动到父元素的边上或者上一个浮动元素的边上。

- 浮动的元素不再占空间了。

- 浮动的元素层级高于普通元素(没有浮动)。

- 浮动的元素一定是块元素，不管以前是什么元素。换句话：行内元素浮动以后，也变成了块元素。

  

### 2.清除浮动

- clear：清除浮动，取值：left、right、both(两者)`clear:both;`
- 一般情况下，上面有浮动，下面就得清除浮动
- 先浮动，后清除；有浮动，必须要有清除浮动
- 清除浮动后，可以让父元素在“视觉”上包含浮动元素
- 清除浮动后，清除浮动之后的其它元素，将恢复默认排版(不再继承上面的浮动特性)



## CSS选择器优先级

（1）单个选择器优先级
行内样式 > Id选择器 > 类选择器 > 标签选择器>通配符

(2）组合选择器的优先级
`组合选择器`如何确定优先级？
基本思路：`指向越精确，优先级越高`。
平常把不同的选择器假设不同的值：

