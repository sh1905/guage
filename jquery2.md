# 事件编程

绑定事件的几种方法如下：

（1） bind(type,[data],fn),  为元素绑定有关的事件处理程序。案例如下：

<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<script src="jquery-1.8.3.js"></script>
		<script>
			$(function(){
				$('#a').bind('click',function(){
					$('img').fadeIn(1000);
				});
				$('#b').bind('click',function(){
					$('img').fadeOut(1000);
				});
			})
		</script>
	</head>
	<body>
		<input id="a" type="button" value="显示" />
		<input id="b" type="button" value="隐藏" />
		<img src="index_22.jpg" />
	</body>
</html>

（2）bind({type:fn,type:fn}),    为一个元素绑定多个事件，参数是一个json对象。



```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<script src="jquery-1.8.3.js"></script>
		<script>
			$(function(){
				$('div').bind({'mouseover':function(){
					$('span').html('哈哈');},
					'mouseout':function(){
						$('span').html('嘻嘻');
					},'click':function(){
						$('span').html('呀哎呀')
					}
				})
			})
		</script>
		<style>
			div{
				width: 20px;
				height: 40px;
				background-color: greenyellow;
			}
		</style>
	</head>
	<body>
		<div></div>
		<span></span>
	</body>
</html>

```



(3)one(type,[data],fn),       为元素绑定事件，和第一个类似，区别就是这个绑定之后只能触发一次，一次之后就没有效果了。

（4）unbind([type])， 移除事件，就是移除给元素绑定的事件

# 事件绑定中的this对象：

this在这一章节中算是非常重要的知识点了，我们要知道this指代的是什么对象。

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<script src="jquery-1.8.3.js"></script>
		<script>
			$(function(){
				$('input').click(function(){
					console.log(this)
				});
				$('div').click(function(){
					this.style.backgroundColor='red';
					$(this).css({width:'400px',height:'400px'});
				});
			})
		</script>
		<style>
			div{
				width: 20px;
				height: 40px;
				background-color: greenyellow;
			}
		</style>
	</head>
	<body>
		<div></div>
		<input type="button" value="单击" />
	</body>
</html>

```

通过上述案例证明：在jquery中，事件绑定中的this指针指向当前要操作的DOM对象。

# 基本动画：

#### show()：显示

show(speed,[callback]) ：以动画效果显示

参数说明：

speed：速度（动画的持续时间）

[callback]：可选参数，事件完成时所触发的回调函数





#### hide()：隐藏

hide(speed,[callback]) ：以动画效果隐藏

参数说明：

speed：速度（动画的持续时间）

[callback]：可选参数，事件完成时所触发的回调函数





toggle() ：切换显示或隐藏

toggle(switch) ：显示或隐藏true：显示false：隐藏

toggle(speed,[callback])：以动画效果切换显示或隐藏

speed:"slow", "normal", "fast"：slow：慢normal：正常fast：快速

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<script src="jquery-1.8.3.js"></script>
		<script>
			$(function(){
				$('input[value=显示').click(function(){
					$('img').show(1000,function(){
						alert('哈哈')
					});
				});
				$('input[value=隐藏').click(function(){
					$('img').hide(1000,function(){
						alert('嘿嘿')
					});
				});
				$('input[value=翻转').click(function(){
					$('img').toggle(1000,function(){
						alert('丫丫')
					});
				});
			})
		</script>
		
	</head>
	<body>
		<input type="button" value="显示" />
		<input type="button" value="隐藏" />
		<input type="button" value="翻转" />
		<img src="index_22.jpg" />
	</body>
</html>

```

#### 淡入淡出效果：

**fadeIn(speed,[callback]) ：以动画形式淡入（显示）**

**fadeOut(speed,[callback]) ：以动画形式淡出（隐藏）**

# 文档操作：

#### 1、在元素内部插入dom元素

（1）在元素内部后面插入

A.append(B) ：将B插入到A的内部的后面

B.appendTo(A) ：将B插入到A的内部的后面 

（2）在元素内部前面插入

A.prepend(B) ：将B插入到A的内部的前面

B.prependTo(A) ：将B插入到A的内部的前面

#### 2、在元素外部插入dom元素

（1）在元素外部的后面

A.after(B)：将B插入到A的外面的后面

B.insertAfter(A)：将B插入到A的外面的后面 

（2）在元素外部的前面 

A.before(B)：将B插入到A的外面的前面

B.insertBefore(A)：将B插入到A的外面的前面

#### 3、删除操作

empty()：清空元素内容。注意：用它清空元素，只是清除标签里面的内容，不清除标签。

remove()：删除元素节点及内容。注意：用它清除的话，不仅仅清除了内容，而且还清除了标签。

#### 4、复制操作

clone() ：克隆（复制）元素，仅仅是复制了元素，并不能复制元素所绑定的事件，不具备事件的功能。

clone(true)：克隆（复制）元素同时复制元素的事件。复制之后的元素具有绑定事件的功能。

#### 5、替换操作

**html()替换**，这种替换仅仅是替换里面的内容，但是不是说就是文本内容，例如一个div标签里面有一个span标签，里面有一段文本。这时用HTML()替换的话，机会把div里面所有的都替换。

replacewith()替换，就拿上面的例子来说，这种替换，会直接替换掉所有的东西，连div标签都会替换掉。

#### 6、包裹操作

用新的标签把原来的标签给包裹起来。

wrap()：对每个元素进行单独包裹

```
//$('div').wrap("<strong></strong>");
              //$('div').wrapAll("<strong></strong>");
              $('div').wrapInner("<strong></strong>");
```

## 7、查找操作

eq(index)：通过元素的索引查找元素，index默认从0开始

filter(expr)：查找与给定元素匹配的元素，expr匹配条件

not(expr)：查找与给定元素不匹配的元素

children([expr])：查找所有子元素

find(expr)：查找所有后代元素

next([expr])：查找紧邻的下一个元素

**nextAll();**查找紧邻的后面的所有元素

prev([expr])：查找紧邻的上一个元素

**prevAll();**查找紧邻的前面的所有元素

parent([expr])：查找当前元素的父元素

siblings([expr])：查找所有同级兄弟节点（无论上下）

