```
<!DOCTYPE html>标准开头
<html>成对标签：格式化和显示的内容
<head>网页的信息
<body>显示在网页的内容
```

<head>
    <title>网站的标题</title>
</head>

```
<body>
	<h1>一级标题
	<h2>二级标题
	<br>换行符
	<p>段落元素，前后各有一个空白行；长的示例文本：输入lorem再按tab，注意有</p>
	<pre></pre>预格式化文本，按照源码的格式显示出来
	<hr>分节，有一个长的横线
	<!--评论-->注释，不显示
	<a href="网页"></a>超链接
```

# hyperlink超链接

## 转向网址

target：_self本身窗口打开; _blank新窗口打开

title:光标悬浮在文字时的提示

网址前要加https://

```
<a href="https://www.google.com" target=_self title="This takes you to Google">
    Google
</a>
```

## 转向邮件

```
<a href="mailto:邮件名@.com" target=_self>
    email me
</a>
```

## 同一文件夹另一个html文件

```
<a href="page2.html" target=_self>
    email me
</a>
```

# 插入图像

图片放在文件中img src="/images/图片名称.png"

alt：屏幕阅读器可以大声朗读的替代文本，残障人士

图片可以单独<img>,放在<a href>里相当于图片是个链接

```
<a href="https://www.bing.com">
	<img src="图片名称.png" height="300" alt="This is a picture of Shrek" title="Shrek is shrexy">
</a>
```

# 插入mp3

> 1. controls显示播放控件
>
> 2. autoplay自动播放
>
> 3. muted静音
>
> 4. loop循环播放
>

```
<body>
	<audio controls autoplay muted loop src="音乐名字.mp3">
```

多个后缀格式适配

```
<audio controls autoplay muted loop>
	<source src="文件名称.mp3" type="audio/mpeg">
	<source src="文件名称.wav" type="audio/wav">
	This browser does not support HTML5 audio.
```

# 插入mp4

和mp3大致相同;autoplay，muted，loop

```
<video controls src="文件名称.mp4" width="500">
```

```
<source src="名称.mp4" type="video/mp4">
<source src="名称.webm" type="video/webm">
```

# 创建图标

放在<head>里

如果图片单独存放在一个文件夹里href="文件夹/favicon.jpg"

```
<link rel="icon" type="image/jpg(或者是其他格式后缀)" href="favicon.jpg">
```

# 文本格式标签

后面都有</相同的字母>

1. <b>加粗
2. <i>斜体
3. <big>大文本
4. <small>小文本
5. <sub>下标
6. <sup>上标
7. <ins>下划线
8. <del>中间删除线
9. <mark>高亮(默认是黄色，可通过style更改颜色)

```
<p>This is <b>bold</b> text</p>
<p>This is <mark style="background-color: lightgreen;">normal</mark> text</p>
```

# 创建列表

## 无序列表（有 · 符号）

> 1. ul列表前后
> 2. li每项前后

```
<ul>
    <li>pizza dough</li>
    <li>tomato sauce</li>
    <li>cheese</li>
</ul>
```

## 有序列表

> 1. ol列表前后
> 2. li每项前后
> 3. type编号的种类：数字、罗马数字、字母......

```
<ol type="A">
    <li>第一项</li>
    <li>第二项</li>
    <li>第三项</li>
</ol>
```

## 描述列表

> 1. dl列表前后
> 2. 不用li
> 3. dt描述术语
> 4. dd描述定义

<dl>
    <dt>HTML</dt>
    <dd>This adds structure to a webpage</dd>
    <dt>CSS</dt>
    <dd>This adds style to a webpage</dd>
    <dt>JavaScript</dt>
    <dd>This adds functionality to a webpage</dd>
</dl>

## 嵌套列表

1. > 使用对应的标签，可以嵌套各种列表

```
<ul>
    <li>pizza dough</li>
    <li>tomato sauce</li>
    <li>cheese</li>
    <li>toppings
        <ul>
            <li>pepperoni</li>
            <li>mushrooms</li>
            <li>peppers</li>
        </ul>
    </li>
</ul>
```

# 创建表格

> 1. table表格标签
> 2. tr行数，每一行有多少列有加多少个th或td
> 3. align对齐方式
> 4. th表格标题
> 5. td表格数据
> 6. 横向合并单元格<td colspan='2'></td>数字是要合并的格数
> 7. 竖向合并单元格<td rowspan='2'></td>
> 8. 横纵向同时合并<td colspan="2" rowspan="2">5</td>
> 9. 横向居中<td style="text-align: center;"></td>
>

<table bgcolor="blue" width="700">
    <tr bgcolor="grey" align="center">
        <th width="100">Sunday</th>
        <th width="100">Monday</th>
        <th width="100">Tuesday</th>
        <th width="100">Wednesday</th>
        <th width="100">Thursday</th>
        <th width="100">Friday</th>
        <th width="100">Saturday</th>
    </tr>
    <tr bgcolor="lightgrey" align="center">
        <td>Closed</td>
        <td>9-5</td>
        <td>9-5</td>
        <td>9-5</td>
        <td>9-5</td>
        <td>9-5</td>
        <td>Closed</td>
    </tr>
</table>

# 添加颜色

body的style：网页的背景色

```
<body style="background-color: black;">
    <h1 style="color:coral">一级标题</h1>
    <h2 style="color:rgb(5, 240, 232)">rgb</h2>
    <h2 style="color:#28f005">16进制</h2>
```

# span和div标签

对元素进行分组

区别：div会对标签内元素分行，span不会

## span

根据结束</span>将部分（若无则为全部）标记颜色

    <p>
        <span style="color: aqua;">Lorem, ipsum dolor sit amet consectetur adipisicing elit.</span> Rem, repellat. Dolore perspiciatis voluptate quibusdam voluptatum dolorem quidem obcaecati tenetur eum? Vel maxime non architecto dolorem eveniet commodi delectus laboriosam numquam.
    </p>

## div

几个段落使用相同的格式：放在一个<div></div>里

```
<body>
    <div style="background-color: burlywood;">
    <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Perspiciatis, omnis. Vitae voluptatem, eum ea omnis earum repellendus ex aliquam in vel, eius eligendi neque quisquam enim delectus mollitia voluptate reprehenderit.
    </p>
    <p>
        <span style="color: aqua;">Lorem, ipsum dolor sit amet consectetur adipisicing elit.</span> Rem, repellat. Dolore perspiciatis voluptate quibusdam voluptatum dolorem quidem obcaecati tenetur eum? Vel maxime non architecto dolorem eveniet commodi delectus laboriosam numquam.
    </p>
    </div>
</body>
```

# 元标记，元数据

介绍关于网页的信息元

> 1. 放在<head>里
> 2. viewport:网页适配移动/pc设备
> 3. refresh刷新频率
> 4. charset使用什么编码

```
<head>
    <title>My first website</title>
    <meta charset="UTF-8">
    <meta name="description" content="Free HTML tutorial for beginners">
    <meta name="keywords" content="HTML, tutorial, beginners">
    <meta name="author" content="Bro Code">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="refresh" content="30">
</head>
```

# frame网页和其他文档嵌入网站中

## 嵌入网页

```
<iframe src="https://www.bing.com" width="750 height="250">
```

## 嵌入文档

```
<iframe src="ad.html" width="750" height="250">
```

### 删除嵌入文档的边框

```
<iframe style="border:0"
src="ad.html" width="750 height="250">
```

# <botton

## 网址转换

- disabled加上后不能点击

### button的属性：style=

> 1. background-color：背景颜色
> 2. color:字体颜色
> 3. border-radius：弧度大小
> 4. font-size：按钮大小，也是字母的大小
> 5. 中间以分号间隔

```
<a href="按钮点击后转向的网址" >
    <button style="background-color: lawngreen;color:#777700;border-radius:20px" disabled>点击按钮</button>
</a>
```

## 执行任务

### button的属性：onclick="doSomething()"

> 1. button里写一次doSomething
> 2. script里写doSomething的函数

```
<button onclick="doSomething()" style="background-color: lawngreen;color:#777700;border-radius:20px">点击按钮</button>
```

```
执行时，Hello会变成Goodbye
<p id="text">Hello</P>

<script>
	function doSomething(){
		document.getElementById("text").innerHTML = “GoodBye”；
	}
</script>
```

# 创建表单

> 1. form 表单标签：包含action属性
> 2. div分块，可和br一起用
> 3. placeholder：占位符，预示的文字
> 4. form后：提交后发送到的界面
> 5. 关联属性的方法——method="GET"或"POST"
>    1. GET：数据附加到网页的url末尾
>    2. POST：提交安全信息（如密码）
> 6. required:不填写时有提示
> 7. value:默认值
> 8. type输入文本的类型（text、password、email、tel、date、number、radio(单选)、checkbox(复选框)
> 9. label:标签
> 10. label for="input的id"
> 11. input:输入
> 12. reset:重置
> 13. 复选框input type="checkbox"
> 14. 单选：放在同一组，要有相同的匹配名称 name="title"
> 15. 输入类<input>，类型选各种；选择类<select>
> 16. 选择文件格式，以逗号分隔
> 17. 评论：row行数，cols列数
> 18. 发送大文件如图像时，需要加enctype

<form action="action_page.php" method="POST" enctype="multipart/form-data">
<div>
<label for="fname">first name:</label>
<input type="text" id="fname" name="fname" placeholder="Spongebob" required>
</div>
<br>

<div>
<label for="lname">last name:</label>
<input type="text" id="lname" name="lname" placeholder="Squarepants" required>
</div>

<br>

<div>
<label for="pass">password:</label>
<input type="password" id="pass" name="pass" maxlength="12" required>
</div>

<br>

<div>
<label for="email">email:</label>
<input type="email" id="email" name="email" placeholder="SPants@gmail.com" required>
</div>

<br>
        
<div>
<label for="phone">phone #:</label>
<input type="tel" id="phone" name="phone" placeholder="(123)-456-7890" pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}">
</div>

<br>

<div>
<label for="bdate">bithdate:</label>
<input type="date" id="bdate" name="bdate">
</div>
<br>

<div>
<label for="quantity">quantity:</label>
<input type="number" id="quantity" name="quantity" min="0" max="99" value="1">
</div>

<br>

<div>
<label for="title">title:</label>

<label for="Mr.">Mr.</label>
<input type="radio" id="Mr." name="title" value="Mr.">
<label for="Mrs.">Mrs.</label>
<input type="radio" id="Mrs." name="title" value="Mrs.">
<label for="PhD.">PhD.</label>
<input type="radio" id="PhD." name="title" value="PhD.">
</div>

<br>

<div>
	<label for="payment">payment:</label>
	<select id="payment" name="payment">
		<option value="visa">visa</option>
		<option value="mastercard">mastercard</option>		
		<option value="giftcard">giftcard</option>
	</select>
</div>

<br>

<div>
	<label for="subscribe">subscribe:</label>
	<input type="checkbox" id="subscribe" name="subscribe">
<div>

<br>

<label for="comment">评论：</label>
<textarea id="comment" row="3" cols="25"></textarea><br>

<label for="file">选择文件:</label>
<input type="file" id="file" accept="image/jpeg, image/png"><br> 

<div>
<input type="reset">
</div>

<br>

<div>
<input type="submit">
</div>
</form>

# 页眉、页脚

版权符号&copy;

页眉<header>

中间<main>

页脚<footer>

字符变小一点<small>

```
<header style="background-color: chartreuse;">
    <h1>Welcome to Bro Code</h1>
    <a href="">Home</a>
    <a href="">About us</a>
    <a href="">Products</a>
    <a href="">Contact us</a>
    <hr>
</header>
```


<main>
    <h4>Check out these cool moves:</h4>
    <image src="if i die young.jpg" alt="a picture of if i die young"></image>
    <P>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Reiciendis illo fugit ea animi enim accusantium tempore ab perspiciatis laudantium consectetur, accusamus praesentium nostrum quos pariatur asperiores eaque nulla saepe minima.</P>
</main>

<footer style="background-color: chartreuse;">
    <hr>
    author: Bro Code<br>
    &copy;copright reserved<br>
    <small><a href="mailto:L17345437447@163.com">L17345437447@163.com</a></small>
</footer>
