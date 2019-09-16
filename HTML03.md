# 表单介绍

## 表单的工作原理:

```
填写有表单的网页，单击某个按钮提交表单。
服务器上有专门的程序(Python程序或者其他PHP语言)，对提交的表单数据进行验证。
如果验证通过，服务器会返回一个成功的消息。
如果验证失败，服务器会返回一个失败的消息
```

```
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8"/>
    <title>网站</title>
    <style>
        div{
        color:red;
        }
    </style>
</head>
<body>
<div>
<form action="http://httpbin.org/post" method="post" enctype="multipart/form-data"/>
<table>
    <caption>我的表格</caption>
    <tr>
        <td>姓名：</td>
        <td><input type="text" name="usname" value="" placeholder="姓名"/> </td>
    </tr>
    <tr>
        <td>年龄：</td>
        <td><input type="password" name="password" value="" placeholder="年龄"/> </td>
    </tr>
    <tr>
        <td>家庭住址：</td>
        <td><textarea name="content" rows="2" cols="20"></textarea> </td>
    </tr>
    <tr>
        <td>描述：</td>
        <td><textarea name="content" rows="3" cols="23"></textarea></td>
    </tr>
    <tr>
        <td>性别：</td>
        <td><input type="radio" name="sex" value="1"/><span>男</span>
            <input type="radio" name="sex" value="2"/><span>女</span>
            <input type="radio" name="sex" value="3"/><span>gay</span>
        </td>
    </tr>

    <tr>
        <td>爱好：</td>
        <td>
            <input type="checkbox" name="hobby" value="1"/><span>足球</span>
            <input type="checkbox" name="hobby" value="2"/><span>篮球</span>
            <input type="checkbox" name="hobby" value="3"/><span>乒乓球</span>
            <input type="checkbox" name="hobby" value="4"/><span>悠悠球</span>
        </td>
    </tr>

    <tr>
        <td>城市：</td>
        <td>
            <select name="城市列表"/>
            <option>...请选择</option>
            <option value="1">安徽</option>
            <option value="2">河南</option>
            <option value="3">北京</option>
            <option value="4">南京</option>
            <option value="5">东京</option>
        </td>
    </tr>
    <tr>
        <td>留言：</td>
        <td><textarea name="content" rows="2" cols="20"></textarea> </td>
    </tr>
    <tr>
        <td><input type="submit" value="登陆"/> </td>
        <td><input type="reset" value="重置"/> </td>
    </tr>
</table>
</div>
</body>
</html>
```

### form标记——块元素

```
name：表单名称。用来区分不同的表单，JS可以通过name的值，对表单进行前端的验证。
method：表单数据的发送方式，取值：get和post
action：指定表单数据的处理程序。一般是服务器端的脚本程序(PHP/Python)。如果为空，则提交给自己来处理。
enctype：表单数据的一个加密(编码)方式。enctype属性只能在 method = post 的表单中。
	application/x-www-form-urlencoded   所有字符都进行加密，这种方式不能上传附件
	multipart/form-data //只对附件进行加密码(编码)，不对普通字符进行编码，如果上传文件，必须使用该值。
```

### GET方法和POST方法

(1)GET提交方法(表单的GET方式不常用)
GET提交的表单，它是把表单中的数据(名称=值)，追加到action处理程序的后面，向服务器发送。
GET提交的表单数据，是在地址栏显示的。

GET提交方法的特点：

```
相对来说不太安全，因为密码不应该显示在地址栏。
不能传递海量数据，因此地址长度有限制。url字符最大长度65535
最大不能超过4kb chrome8k
不能上传附件。
只要是通过地址栏，向服务器传数据的，一定是GET传递方式。
```

2)post提交方式
POST方式直接将表单数据发给了服务器，`不会在地址栏显示`。
POST的特点

```
相对来说比较安全。包传递
可以传递海量数据，长度没有限制。
可以上传附件。
POST方式只能用在表单中，其它地方不会用来。
```

## [表单中的各元素]

### 1.单行文本域：用户名、地址、电话、邮箱等

语法格式：`<input type = “text” 属性 = “属性值” />`
常用属性:

```
type：元素的类型。取值：text、password、radio、checkbox、button、submit、reset等。
name：表单元素的名称。可以包含a-z、A-Z、0-9、_这些符号，但不能以数字开头。
value：元素的值。
size：文本框的长度，以字符为单位。
maxlength：最多可以输入的字符数
readonly：只读属性。如：readonly = “readonly”
disabled：禁用属性。如：disabled = “disabled”
```

### 2.单行密码框

语法格式：`<input type = “password” 属性 = “属性值”  />`
常用属性:

```
type：元素的类型。
name：元素的名称
value：元素的值
size：密码框的长度，以字符为单位
maxlength：最多可以输入的字符数
readonly：只读属性。如：readonly = “readonly”
disabled：禁用属性。如：disabled = “disabled”
```

### 3.单选按钮

语法格式：`<input  type = “radio” 属性 = “属性值” />`
常用属性

```
type：元素类型
name：元素名称
value：元素的值
checked：是否默认选中。如：checked = “checked”
```

### 4.复选框

语法格式：`<input  type = “checkbox” 属性 = “属性值” />`
常用属性:

```
type：元素类型
name：元素名称
value：元素的值
checked：是否默认选中。如：checked = “checked”
```

### 5.下拉列表

想去什么地方旅游:
<select name="dot">
	<option value="">..请选择</option>
	<option value="1">巴厘岛</option>
	<option value="2">马尔代夫</option>
	<option value="3">巴黎</option>
	<option value="4">悉尼</option>
	<option value="5">千锋</option>
</select>

### 6.文本区域

常用属性:

```
name：元素名称
value：元素的值，不能直接给<textarea>元素添加value属性。
cols：宽度，是多少个字符宽。
rows：几行的高度。
```

### 7.上传文件域

语法格式：<input  type = “file”  属性 = “属性值”  />

<form name="uploadFile" method="post" action="upload.php" enctype="multipart/form-data">
	<input type="file" name="upload"  id="" value=""/>
</form>

### 9.表单中的各种按钮

提交按钮：提交表单。如：`<input  type = “submit”  value = “提交表单”  />`
重置按钮：重新填写。如：`<input  type = “reset”  value = “重新填写”  />`
图片按钮(不常用)：指定图片的路径，功能也是提交表单。如：`<input type="image" src="images/btn02.png" />`
普通按钮：不具备任何功能，一般要绑定JS程序，来实现各种功能。

```
<input type="submit" id="" value="提交表单">
<input type="reset" value="重置">
```

