# css

## [CSS 语法格式]

```


<style type="text/css">
	h1 {color:red;font-size:12px;}
</style>
- 一个CSS规则,由`选择器`和CSS格式构成的.
- "选择器"选择了一个HTML标记,并给其加上样式.
- "CSS"格式是放在`{}`中.CSS格式是有多条语句构成.
- 每一条CSS格式语句必须以`英文格式`下的`;`结束,最后一条可以不加;
- 每一条CSS格式语句是由`属性名:属性值`构成
- "属性名"是CSS中规定的,不能自己定义.


```

## [CSS 选择器]

(1)通配符`*`

- 描述:将代表HTML所有的标签
- 注意:通配符的兼容性不是太好,`IE6不支持的`
- 举例:`*{color:red;font-size:12px;text-align:center;}

(2)标签选择器

- 描述:标签选择器于HTML标签一一对应,但是不加`</>`

比如:

<style type="text/css">
div{color:blue;font-size:12px;background-color:yellow;}
</style>

```
<div class="div">
你好
</div>
```

## (3)类选择器

- 描述:给一类的HTML标记添加样式.只要HTML标记的`class`属性是一样的,浏览器就认为是一类.
- HTML里的公共属性,就是每个标签都可以拥有的属性;比如`id`,`name`,`class`,`style`,`title`等.
- 说明:类选择器,是以小数点开头的`.`,比如`.div{color:red;}`.
- 同一个类样式可以给不同的HTML,一个HTML`class`属性可以包含多个类样式;

.style_1{color:blue;}
.style_2{font-size:12px};
.style_3{border:1px solid red};

<p class='style_1 style_2 style_3'>样式1</p>
<p class='style_1 style_2'>样式2</p>
<p class='style_1'>样式3</p>

## (4)id选择器

- 描述:给网页中指定id属性的HTML样式.
- 要求:在一个网页中，不能有多个相同id值的元素。id相当于身份证号码，只能使用一次(具有唯一性)。
- 说明：`class属性用来给元素添加CSS的，而id属性一般是用来加JS的`
- id选择器命名：必须以“#”开头命名。

# 二、组合选择器

## （1）多元素选择器

- 描述：同时给多个元素，加同一种样式。多个元素之间用英文下的逗号隔开.

比如:

```
ul,ol,li,dl,dt,dd{margin:0px;padding:0px;}
```

## (2)后代元素选择器

- 描述:给某个元素的所有后代元素，添加样式。两个选择器之间用空格隔开.

`<div><sapn></span></div>`这里面的`span`就是`div`的后代元素.
比如:

```
#div h2{color:blue;border:1px solid blue;background-color:yellow;}
```



<div id='div'>
	<h2>新闻标题1</h2>
	<div>
		<h2>新闻标题2</h2>
	</div>
</div>

## （3）子元素选择器

比如:

```
#div>h2{color:blue;border:1px solid blue;background-color:yellow;}
```



<div id='div'>
	<h2>新闻标题1</h2>
	<div>
		<h2>新闻标题2</h2>
	</div>
</div>

## 二、伪类选择器

- 伪类选择器，一般是用来选择`<a>`元素的。
- 超级链接有四种状态：正常状态、放上状态、访问过状态、激活状态。
- 四种状态正好对应四种选择器。
  - `:link` 正常链接效果。
  - `:visited` 访问过的效果
  - `:hover` 鼠标放上的效果
  - `:active` 激活状态(鼠标点击的一瞬间出现一般不用)
  - `这4个的顺序一定不能弄错,弄错了就没有效果`
- `text-decoration`属性
  - `none`     默认。定义标准的文本。
    - `underline`定义文本下的一条线。
    - `overline`定义文本上的一条线。
    - `line-through`定义穿过文本下的一条线。
    - `blink`定义闪烁的文本。

### [CSS尺寸属性]

- width：元素的宽度。
- height：元素的高度

### [CSS字体属性]

- font-size：文字大小。

- font-weight：加粗效果。取值：bold

- font-style：斜体效果。取值：italic

- font-family：字体。

  

### [CSS文本属性]

- color：文本颜色。

- line-height：行高，可以是百分比，也可以是固定值。

- text-align：文本的水平对齐方式，取值：left、center、right

- letter-spacing：字间距。

- text-decoration：文本修饰线，取值：underline(下划线)、none、overline(上划线)、line-through(删除线)

- text-indent：首行缩进

  

[px和em以及rem]

- px像素（Pixel）。相对长度单位。像素px是相对于显示器屏幕分辨率而言的。
- em是相对长度单位。相对于当前对象内文本的字体尺寸。如当前对行内文本的字体尺寸未被人为设置，则相对于浏览器的默认字体尺寸。em是根据父类的变化而变化的
- rem和em类似,`rem:root em`;相对于根的比较;
- 默认的大小是16px

