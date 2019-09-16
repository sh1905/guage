# 1、什么是jquery

jQuery是一个开源的，优秀的javascript函数库(js框架)，他体积小，简化了很多对HTML、CSS、DOM、事件、动画的处理。

## jQuery中的选择器

#### ***1.基本选*择器**：

就是直接找到各个标签，然后进行操作。例如对某个标签设置格式就是如下：

$('标签').css('background','red')

<!DOCTYPE html>
<html>

	<head>
		<meta charset="utf-8">
		<title></title>
		<script src="jquery-1.8.3.js"></script>
		<script>
			$(function() {
				$('#a').css('background', 'red');
				$('.b').css('background', 'pink');
				$('p').css('background','yellow');
			})
		</script>
	</head>
	
	<body>
		<div id="a"><span>好好学习</span></div>
		<p>天天向上</p>
		<span class="b">国泰民安</span>
	</body>

</html>

#### ***2.层级选择器：***

1.选择一个元素所有的后代元素，可以跨层寻找，格式是两个标签之间隔了一个空格来连接。

2.选择一个元素的所有子元素，仅仅是子元素，只能是这个元素下面的一级，类似于它的儿子，格式是两个标签用>连接。

3.选择与一个元素同级的并且紧邻着该元素的下一个元素，格式是两个标签用+连接。

4.选择与一个元素同级的所有元素，格式是两个标签用~连接。

具体事例如下：

<!DOCTYPE html>
<html>

	<head>
		<meta charset="utf-8">
		<title></title>
		<script src="jquery-1.8.3.js"></script>
		<script>
			$(function() {
				$('div p').css('background','pink');
				$('div>span').css('background','red');
				$('p:first+span').css('background','blue')
				$('p~span').css('background','pink');
			})
		</script>
	</head>
	
	<body>
		<div>
			<p>hi</p>
			<span>yaya</span>
			<p>heihei</p>
			<span>lala</span>
			<table>
				<tr>
					<td>we</td>
					<td>are</td>
				</tr>
		</div>
		</table>
	</body>

</html>

#### ***3.简单选择器：***

标签:first    选择第一个标签

标签:last   选择最后一个标签

标签:even    选择第偶数个标签

标签:odd    选择第奇数个标签

标签：not(标签1)   选择除了标签1之外的所有标签

<!DOCTYPE html>
<html>

	<head>
		<meta charset="utf-8">
		<title></title>
		<script src="jquery-1.8.3.js"></script>
		<script>
			$(function() {
				$('li:first').css('background','pink');
				$('li:last').css('background','pink');
				$('li:even').css('background','pink');
				$('li:odd').css('background','red');
				$('li:not(li:eq(0))').css('background','grey')
			})
		</script>
	</head>
	
	<body>
		<ul>
			<li>hah</li>
			<li>heihei</li>
			<li>lala</li>
			<li>eee</li>
		</ul>
	</body>

</html>

#### ***4.内容选择器：***

标签:contains(text)      查找包含指定内容的标签

标签:empty     查找内容为空的标签

标签:has(selector)      查找含有指定选择器的标签

标签:parent       查找具有子元素的元素

<!DOCTYPE html>
<html>

	<head>
		<meta charset="utf-8">
		<title></title>
		<script src="jquery-1.8.3.js"></script>
		<script>
			$(function() {
				$("div:contains('大')").css('background','red');
				$('p:empty').css('background','gray');
				$("p:has('span')").css('background','blue');
				$('p:parent').css('background','yellow');
			})
		</script>
	</head>
	
	<body>
		<div>快乐大本营</div>
		<p><span>向往的生活</span></p>
		<span>极限挑战</span>
		<p style="width: 20px;height: 20px;"></p>
		<table>
			<tr>
				<td>哈哈</td>
			</tr>
		</table>
		<div></div>
	</body>

</html>

#### ***5.可见性选择器：***

标签:hidden   查找所有被隐藏的标签(display:none 和 input type='hidden')

标签:visible     查找所有可见元素（display:block)

注意：当有标签被隐藏或者想显示时，可以使用以下两种方法：

标签.show()     和      标签.hide()

<!DOCTYPE html>
<html>

	<head>
		<meta charset="utf-8">
		<title></title>
		<script src="jquery-1.8.3.js"></script>
		<script>
			$(function(){
				$('div:hidden').css('background','red');
				$('div:hidden').show()
				$('p:visible').css('background','blue');
				$('p:visible').hide();
			})
		</script>
	</head>
	<style>
		div{
			width: 100px;
			height: 100px;
			background-color: #7FFF00;
			display: none;
		}
	</style>
	<body>
		<div>你好</div>
		<p>你在干什么</p>
	</body>

</html>

#### ***6.属性选择器：***

<u>[attribute] ：匹配具有指定属性的元素**</u>

<u>[attribute=value]：匹配属性值等于value的元素</u>

<u>[attribute!=value] ：匹配属性值不等于value*的元素</u>

<u>[attribute^=value] ：匹配属性值以value开始的元素</u>

<u>[attribute$=value] ：匹配属性值以value结尾的元素</u>

<u>[attribute*=value] ：匹配属性值包含value的元素</u>

<u>[selectorN]：匹配包含多个属性的元素**


		<!DOCTYPE html>
	<html>
	
		<head>
			<meta charset="utf-8">
			<title></title>
			<script src="jquery-1.8.3.js"></script>
			<script>
				$(function(){
	//				$('div[name]').css('background','red');
	//				$('div[name=age]').css('background','blue');
	//				$('div[name!=age]').css('background','blue');
	//				$('div[name^=use]').css('background','red');
					$('div[name$=me]').css('background','blue');
	
	
				})
			</script>
		</head>
		
		<body>
			<input type="text" name="username" />
			<div name="username">极限挑战</div>
	    <div name="userage">1234</div>
	    <div name="age">abcdef</div>
	    <div name="username">程咬金</div>
	    <div name="userage">12</div>
	    <div name="age">haha</div>
		</body>
	
	</html>

</html>

#### ***7.表单选择器：***

标签:input ：匹配所有表单元素

标签:text ：匹配所有文本框

标签:password：匹配所有密码框

标签:radio ：匹配所有单选按钮

标签:checkbox：匹配所有复选框

标签:submit ：匹配提交按钮

标签:reset：匹配重置按钮

标签:image：匹配图片

标签:button：匹配按钮

标签:file：匹配文件域

标签:hidden：匹配隐藏表单



#### ***8.表单属性选择器：***

:enabled ：匹配所有可用元素

:disabled ：匹配所有不可用元素

:checked ：匹配复选框单选框所有选中元素

:selected ：匹配下拉选框所有选中元素

```
       把禁用的元素设置为开启状态
       $(":disabled").attr('disabled',false);
       把开启的元素设置禁用状态
       $(":enabled").attr('disabled',true);
       获取单选框里面的值
       alert($(":checked").val());
```

# 2.dom对象和jquery对象

dom对象：使用document.getElementById或document.getElementsByTagName获取的对象就是dom对象。

jquery对象：使用$符号选择的元素就是jquery对象。

**dom对象和jquery对象的互相转换：**

(1) jquery对象转换成dom对象：

dom对象=jquery对象[下标];

dom对象=jquery对象.get(下标);

```
$('div')[1].style.backgroundColor='green';
$('div').get(2).style.backgroundColor='red';
```

(2)dom对象转换成jquery对象：

jquery对象=$(dom对象)；

```
 var div2 = document.getElementsByTagName('div')[2];
 $(div2).css('background','red');
```

**jQuery对象的实质就是一个数组，每个数组元素本质就是一个DOM对象**

# 3.jQuery的属性

#### ***1.attr属性：***

attr(name)：获取指定元素的属性

attr(key,value)：设置元素的属性

attr(object)：为元素同时设置多个属性，要求参数是一个json数据

attr(key,fn)：通过函数的返回值设置元素属性

removeAttr(name)：移除元素属性

```
  //获取img的src属性
       //alert($('img').attr('src'));//one.jpg
       //设置img的src属性，
       //$('img').attr('src','two.jpg');
       //设置img的多个属性值属性，
       //$('img').attr({src:'two.jpg',width:'600',height:'200'});
```

#### ***2.class属性：***

addClass(class)：为元素添加class属性

removeClass(class)：移除元素的class属性

toggleClass(class)：切换样式，如果元素不存在该属性则添加，否则移除

hasClass(class)：判断元素是否具有某个css类样式

```
 //给div1添加 class属性。
        //$("#one").addClass('one');
        //给div2删除 class属性
        $('#two').removeClass('two');
```

#### ***3.css属性：***

```
 //给id=one的div添加高度，宽度，背景颜色  $("div").css({width:'200px',height:'200px','background':'red'});
```

#### ***4.offset位置：***

```
//设置div的位置
//注意值是json格式的
$('div').offset({
 top:'200',
left:'200'
```

#### ***5.元素的尺寸：***

width()**：获取元素的宽度

width(value)：设置元素的宽度

height()：获取元素的高度

height(value)：设置元素的高度

```
//获取元素的高度和宽度
    console.log($('#one').width());//250
    console.log($('#one').height());//150
 //设置元素的高度和宽度
    $("#one").width(400);
    $("#one").height(300);

```

#### ***6.文本域值：***

html()：获取元素的值

html(val)：设置元素的值

```
 //获取元素的文本
    console.log($('#one').html());
  //设置元素文本
    $("#one").html("<strong>你好</strong>");
```

val()：获取表单元素的值

val(val)：设置表单元素的值

```
  //获取表单域里面的值
   console.log($('input[name=username]').val());
    //设置表单域里面的值
  $('input[name=username]').val('请求输入你的姓名')
```

text()：获取元素的值

text(val)：设置元素的值

```
 //获取表单域里面的值
   console.log($('div').text());
   console.log($('div').html());
   //设置表单域里面的值
    $("#one").html("<font color='red'>大家好</font>");
    $("#two").text("<font color='red'>大家好</font>");
```

**html()获取的是标签里面所有的内容，不仅仅是文本内容，如果有标签的话也会被获取，例如一个p标签里面包含了一个span标签，里面又包含了一句文本。这时候用html来获取的话，会获取span标签加文本，而用text()来获取的话，只能获取里面的文本。**

# 4.jQuery的事件

**1.页面加载事件：**

```
（1）$(document).ready(function(){ 

//事件的处理程序

}); 
```

```
（2）$(function(){
	//事件的处理程序
});
```

```
（3）$().ready(function(){ 

​```
//事件的处理程序
​```

}); 
```

**2.常用的事件：**

->  blur(fn)：失去焦点时触发   (输入框中突然失去选中状态)
->  change(fn)：状态改变时触发   (输入框每输入一个字符)
=>  click(fn)：点击时触发

->  keypress(fn)：键盘按下时触发

->  mousedown(fn)：鼠标按下时触发

->  mouseover(fn)：鼠标悬浮时触发
->  mouseout(fn)：鼠标离开时触发

->  scroll(fn)：滚动时触发

**3.事件的切换：**

hover(over,out)：鼠标悬浮与鼠标离开事件

参数说明：

over：鼠标悬浮事件

out：鼠标离开事件 

```
/*$("img").mouseover(function(){
                $('img').attr('src','two.jpg');
       }).mouseout(function(){
                $('img').attr('src','one.jpg');
       });*/

  	   //hover(function,function)
       $('img').hover(function(){
                $('img').attr('src','two.jpg');
       },function(){
            $('img').attr('src','one.jpg');
       });
       
       
   toggle() 方法切换元素的可见状态。

参数:
speed:可选。规定元素从可见到隐藏的速度（或者相反）。默认为 "0"。如果设置此参数，则无法使用 				switch 参数。
callback:可选。toggle 函数执行完之后，要执行的函数。除非设置了 speed 参数，否则不能设置该参			
switch:可选。布尔值。规定 toggle 是否隐藏或显示所有被选元素。
				True - 显示所有元素
				False - 隐藏所有元素
 如果设置此参数，则无法使用 speed 和 callback 参数
```

