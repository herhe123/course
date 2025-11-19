层叠样式表*C*ascading *S*tyle *S*heets

1. 内置表情符号选择：win+分号
2. 2rem 200%

# 适用

**外部css**

<head里

```
<link rel="stylesheet" href="style.css">
```

**内部css**

<head里<style>部分

```html
<style>
h1 {
  color: maroon;
  margin-left: 40px;
} 
</style>
```

**行内css**

```html
<h1 style="color:blue;text-align:center;">This is a heading</h1>
<p style="color:red;">This is a paragraph.</p>
```

多个样式表读取最后设置的

# 元素选择器

```html
/* 根据id分类 */
<p id="p1"></p>
<p id="p2"></p>
/* 奇偶分类 */
<p id="p1" class="odd"></p>
<p id="p2" class="even"></p>
<p id="p3" class="odd"></p>
<p id="p4" class="even"></p>
```

> 1. 有id的         #id
> 2. 有class的（优先class）      .class
> 3. *:选取所有元素

# color

> 1. 背景色background
> 2. color字体颜色
> 3. body{}整体背景色
> 4. hsl第二个数值越大，越深；第三个数值越小，越深

# font

> 1. 找字体网站fonts.google.com
>    - serif是有衬线字体
> 2. 字体种类font-family:"字体1","字体2"，sans-serif;
>    - 字体名称中包含空格，放在引号里"lucida console", "courier new";
>       - verdana, arial;	
> 3. 导入外部字体：html界面-head里粘贴<link href=>
> 4. 字体名字font-family
> 5. 字体大小font-size：
>    - 正常是16px
>    - 1.1em是110%，1.5em是150%，0.5em是50%
> 6. 斜体font-style: italic;
>    - font-syle: normal;
> 7. 粗体font-weight: bold;
> 8. 下划线text-decoration:cyan wavy unferline;
>    - wavy波浪形，dotted点状，double双划线 cyan下划线颜色（这里指青色）

本地安装，创建fonts文件夹，把解压后的ttf放到fonts文件夹

下载本地后可删除html中引用的外部链接，font-face

@font-face 创建字体规则

```
@font-face {
    src: url(fonts/Mulish-VariableFont_wght.ttf);
    font-family: Mulish-VariableFont_wght;
}
@font-face {
    src: url(fonts/Heebo-VariableFont_wght.ttf);
    font-family: Heebo-VariableFont_wght;
}

h1{
    font-family: Mulish-VariableFont_wght, "arial";
}
p{
    font-family: Heebo-VariableFont_wght.ttf, "lucida console", "courier new";
    font-size: 20px;
    font-weight: bold;
    font-style: italic;
}
```

# borders

> 1. border-style: solid;
>    - solid直线，dashed虚线，double双横线，ridge浮雕，groove雕刻，inset陷入，outset突出
> 2. border-width边框宽度
> 3. border-color边框颜色
> 4. style,width,color可简化为border: solid, 5px, red;
> 5. border-radius边框圆角
> 7. border-top/bottom/left上/下/左边框
> 10. 上下左右边框的style,width,color同样可像上述简化

```
border:5px solid;
border-top-style:dotted;
border-left-width:20px;
```

## padding

==**内部**文本和边框的（上下左右）间距==

注意边框内图片和文字的距离，文字和边框的距离

```css
/* 上下 | 左右 */
padding: 5% 10%;

/* 上 | 左右 | 下 */
padding: 1em 2em 2em;

/* 上 | 右 | 下 | 左 */
padding: 5px 1em 0 2em;
```

# shadows

- 左右，上下，扩散
- 两个为双重阴影

text-shadow：**文本阴影**

```
text-shadow: -5px 0px 0px greenyellow;5px 0px 0px red;
```

box-shadow：**边框阴影**

```
<div id="box1"></div>
```

```
#box1{
    box-shadow: 5px 5px 5px pink;
}
```

```
h1:hover{
	box-shadow:5px 5px 5px pink;
}
```

# margins

元素外部空出的空间（边框外部和页面间的距离）

> 1. margin-left/bottom单位：px像素，%百分比，**auto**根据窗口大小固定在margin相反一侧
>
> 2. margin-left=auto 且 margin-right=auto时：水平居中
>
> 3. margin-bottom和下一个盒子的距离
>
> 4. margin:10px;上下左右同时调
>
> 5. [`auto`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/margin#auto)
>
>    让浏览器自己选择一个合适的外边距。有时，在一些特殊情况下，该值可以使元素==居中==。

```css
/* 上下左右同时调 */
margin:10px;

/* 上下 | 左右 */
margin: 5px 10px;

/* 上 | 左右 | 下 */
margin: 1px 3px 2px;

/* 上 | 右 | 下 | 左 */
margin: 5px 1px 0 2px;
```

# float

允许其他元素在周围流动，针对图像和块级元素<div>

插入图片时，可以分别id

```
<img src="1.jpg" height:"150px" id="img1">
```

```css
/* 在右侧的两种方法 */
img{
    float:right;
}
#img1{
	float:left;
}
```

```css
/* 盒子在左侧 */
.box{
	float:right;
}
```

**图片不溢出整体边框**

```
body{
	display:flow-root;
}
```

**清除浮动**

```
display:block;
clear:both;
```

忽略边框、padding

```
float:left;
box-sizing: border-box;
```

# overflow

1. visible默认溢出可见

2. hidden隐藏，复制时仍存在(如：计算器的方程显示框)
3. clip隐藏
   - 同时设置overflow-clip-margin:13px(指控制溢出的像素)
4. scroll带左右上下滚动条，若文字不足仍显示滚动条，但禁止使用状态
5. auto根据文字多少适配是否出现滚动条

```
div{
    border: solid 5px pink;
    height: 50px;
    overflow: clip;
    overflow-clip-margin: 20px;
}
```

# display

**block-level**

块级元素，从新行开始，占据整个可用宽度

如：h1,div,p,header,footer

**inline**

内联元素，不从新行开始，元素的宽度限于本身需要的

无法自定义设置width,height

如：span,a,img

```
<div>div</div>
<span>span</span>
div{
    background-color: hsl(0, 100%, 50%);
    height: 100px;
    width: 100px;
}
span{
    background-color: hsl(75, 100%, 50%);
}
```

display:

- block：元素设置为块级元素，可以自定义宽度、高度

- inline：元素设置为内联元素

- inline-block：不占用新行，但可以设置宽度、高度

- none：删除该元素，且位置被占用

-   display: inline-block;

    visibility: hidden;元素消失，位置仍空出留存

- flex弹性盒

- grid元素排列在网格中

  - grid-template-columns列数（4列），1fr是单位
  - gap元素之间的间隙

- flow-root：float元素不溢出div外

  ```
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
  ```

# width height

width:50%

height:auto（自动适配需要的高度，div默认是auto）

padding: 25px;

忽略width和padding——==box-sizing: border-box;==

```css
* {
	box-sizing: border-box
}
```

- max-width：小于->窗口宽度；大于->设置的最大宽度

# position

规定元素的定位类型

1. static:默认位置，top,right,bottom,left失效
2. relative:元素先放置在未定位时的位置，在不改变页面布局下，调整元素位置，有预留空间<img src="C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20240412173702072.png" alt="image-20240412173702072" style="zoom:50%;" />
3. fixed:元素被移出正常文档流，无预留空间，元素位置时相对于屏幕视口的，屏幕滚动时相对位置不变，适用广告
4. absolute:无预留空间，元素相对于最近的非 static 定位祖先元素的偏移
5. sticky:???类似fixed，会保留元素位置

# background images

background-image: url("背景图.jpg");

background-repeat: no-repeat;尺寸小的时候，不重复图片

background-position: center;位置中心

background-attachment: fixed;随窗口缩放

background-size: cover;占据整个页面

# 对齐

- 块级元素<div>：margin:auto;

  - ==需设置width属性==

    ```css
    #container{
        margin: auto;
        width: 40%;/* 不溢出，不是100%即可 */
        border: 2px solid;
    }
    ```

- 文本：  text-align: center;

  - 1、2方式组合可元素、文本都居中

- 图像：先设置为块级元素，再左右居中

  ```css
  img{
      display: block;
      margin-left: auto;
      margin-right: auto;
  }
  ```

- 左右对齐：

  - 方法一：position：absolute;

    ```
    position: absolute;
    right: 0px;
    ```

  - 方法二：float：right;

- 垂直对齐：设置padding

- 水平垂直居中：

  ```
  display: flex;
  justify-content: center;
  align-items: center;
  ```

# combinators组合器

```html
<div id="container">
    <p>This is #1</p>
    <p>This is #2</p>
    <div>
        <p>This is #3</p>
    </div>
</div>

<p>This is #4</p>
<p>This is #5</p>
```

**后代组合器：空格**

指定元素的所有后代

```
#container p{
    background-color: red;
}
```

**直接子代组合器： >**

指定元素的所有子元素

**一般兄弟组合器： ~**

指定元素的**同级**、**所有**元素（本例为4、5）

**紧邻兄弟组合器： +**

指定元素的**相邻**、**同级**元素（本例为4）

# pseudo-classes伪类

1. link：未访问的链接

2. visited：已访问的链接

3. hover：悬停时

4. active：按住时（活动状态）

5. not(:hover)：非伪类的格式设置

6. nth-child()：指定元素匹配

```
a/button:link/hover/active/visited{}
li:hover{}
li:not(:hover){}
li:nth-child(3n){}
li:nth-child(odd){}
```

## ==悬停时出现==

```html
<div id="greeting">Hover here
    <p>Hello</p>
</div>
```

```css
#greeting p{
    background-color: aqua;
    padding:20px;
    display: none;
}
#greeting:hover p{
    display: block;
}
```

# poseudo-elements伪元素

设置元素指定部分的样式

可用于：

1. 设置元素的首字母、首行的样式
2. 在元素的内容之前或之后插入内容

- ::first-letter（首字母）/first-line（首行）/selection（选中部分文本）
- ::marker前面标记元素
  - content元素符号，**有引号**

- ::before前面插入内容
- ::after后面插入内容

```
<h1>Hello</h1>
<p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Voluptate eius iste necessitatibus nulla, eaque velit.</p>
<ul id="fruit">
    <li id="orange">orange</li>
    <li id="lemon">lemon</li>
</ul>
```

```
h1::first-letter{
    font-style:italic;
    font-size: 2em;
}
p::first-line{
    background-color:green;
}
p::selection{
    color: red;
    background-color: black;
}
```

```
#fruit li::marker{
    content:"✔";
    color:aquamarine;
    font-size: 2em;
}
#orange::after{
    content:"🍊";
}
```

# 分页

> 1. 第一个<a>表示前进，在不同页对应不同，首页刷新
> 2. 最后<a>后退，末页刷新
> 3. class="active"当前页数
> 4. .pagination a.active当前页数的css
> 5. .pagination a:hover:not(.active)非当前页悬停时

```
<h1>This is page #1</h1>
<p>Lorem ipsum dolor, sit amet consectetur adipisicing elit</p>
<div class="pagination">
    <a href="index.html"><</a>
    <a href="index.html" class="active">1</a>
    <a href="page2.html">2</a>
    <a href="page3.html">3</a>
    <a href="page4.html">4</a>
    <a href="page5.html">5</a>
    <a href="page2.html">></a>
</div>
```

```
.pagination{
    text-align: center;
}
.pagination a{
    color: black;
    text-decoration: none;
    padding:8px 15px;
    display: inline-block;
}
.pagination a.active{
    background-color: rgb(69, 232, 77);
    font-weight: bold;
    border-radius: 7px;
}
.pagination a:hover:not(.active){
    background-color: beige;
    border-radius: 7px;
}
```

# 下拉菜单

1. dropdown{display: inline-block}
2. 元素设置为absolute
3. 设置阴影

```html
<div class="dropdown">
    <button>Food</button>
    <div class="content">
        <a href="">Apple</a>
        <a href="">Banana</a>
        <a href="">Orange</a>
    </div>
</div>
<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Adipisci illum quae at error, debitis perspiciatis.</p>
```

```css
.dropdown{
    display: inline-block;
}
.dropdown button{
    background-color: hsl(0, 0%, 80%);
    color:white;
    padding:10px 15px;
    border:none;
    cursor: pointer;
}
.dropdown a{
    display: block;
    padding: 10px 15px;
    color:black;
    text-decoration: none;
}
.dropdown .content{
    display: none;
    position: absolute;
    background-color: hsl(0, 0%, 95%);
    min-width: 100px;
    box-shadow: 2px 2px 5px hsl(0, 0%, 0%, 0.8);
}
.dropdown:hover .content{
    display: block;
}
.dropdown:hover button{
    background-color: hsl(0, 0%, 70%);
}
.dropdown a:hover{
    background-color: hsl(0, 0%, 90%);
}
```

# 导航栏

html格式<ul><li><a href=""></a></li></ul>

<nav导航元素

<main主要内容

1. 删除列表的项目符号（list-style-type）和默认的内外边距（margin，padding）

```html
<h1>Bro Code</h1>

<nav class="navbar">
    <ul>
        <li><a href="index.html">Home</a></li>
        <li><a href="about.html">About</a></li>
        <li><a href="products.html">Products</a></li>
        <li><a href="contact.html">Contact</a></li>
    </ul>
</nav>

<main>
    <h3>This is the Products page</h3>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Incidunt commodi dolores ipsum totam tempore exercitationem ratione quasi, in, quae nihil asperiores impedit voluptatem assumenda. Explicabo molestiae temporibus distinctio reprehenderit doloribus.</p>
</main>
```

```css
h1{
    text-align: center;
}
.navbar{
    background-color: hsl(0, 0%, 100%);
}
.navbar ul{
    list-style-type: none;
    background-color: hsl(0, 0%, 25%);
    padding:0px;
    margin:0px;
    overflow: hidden;
}
.navbar a{
    text-decoration: none;
    color: white;
    padding: 15px;
    display: block;
    text-align: center;    
}
.navbar a:hover{
    background-color: hsl(0, 0%, 10%);
}
.navbar li{
    float: left;
}
body{
    margin: 0px;
}
main{
    margin: 20px;
}
```

# 网站布局

semantic tags语义标签

```
<header>标题 介绍性内容，标题、徽标、作者信息
<nav>导航、其他链接
<main>主要（section,aside,article,div)
<section>  相关内容
<aside>和其余页面内容几乎无关的部分，被认为是独立于该内容的一部分并且可以被单独的拆分出来而不会使整体受影响。其通常表现为侧边栏或者标注框
<article>新闻文章、职位发布、博客文章
<footer>页脚  作者信息、版权信息、导航链接
<strong>总计，一般用粗体表示
```

```
*{
	box-sizing: border-box;
}
body{
    margin: 0;
}
header{
    background-color: hsl(0, 0%, 86%);
    text-align: center;
    padding: 25px;
}
.navbar{
    background-color: hsl(0, 0%, 15%);
    height: 50px;
}
aside{
    width: 20%;
    float: left;
    padding: 10px;
}
section{
    width: 40%;
    float: left;
    padding: 10px;
}
article{
    width: 40%;
    float: left;
    padding: 10px;
}
footer{
    display: block;
    clear:both;
    background-color: hsl(0, 0%, 86%);
    text-align: center;
    padding: 25px;
}
```

## 响应式css

跟随窗口大小，改变css布局

```
@media screen and (max-width:600px){
    aside, section, article{
        width:100%;
    }
}
```

# 图标



放在<head>里

```html
<script src="https://kit.fontawesome.com/166ff711be.js" crossorigin="anonymous"></script>
```

```html
<div class="icons">
    <a href="">
        <i class="fa-solid fa-house fa-5x"></i>
    </a>
    <a href="https://youtube.com">
        <i class="fa-brands fa-youtube fa-5x"></i>
    </a>
</div>
```

```css
.icons{
    text-align: center;
}
.icons a{
    text-decoration: none;
    margin-right: 20px;
}
.fa-brands.fa-youtube.fa-5x{
    color: hsl(0, 100%, 50%);
}
.fa-brands.fa-youtube.fa-5x:hover{
    color: hsl(0, 100%, 60%);
}
```

# flexbox

1. flex-direction
   - row默认，行（横向从左排列）
   - row-reverse横向从右排列
   - column竖向排列
   - column-reverse竖向反向排列
2. justify-content：**左右**对齐方式，主轴与x轴的关系
   1. flex-start默认
   2. flex-end靠右
   3. center居中
   4. space-between均匀，内部有空隙，外部无空隙，会随窗口大小改变距离
   5. space-around均匀，外部内部都有空隙
   6. space-evenly
3. align-items：**上下**对齐方式，主轴与y轴的关系
   1. flex-start默认
   2. flex-end放在容器的底部
   3. center//容器本身垂直对齐，若要在页面中间加height：100vh;
   4. baseline无空隙左上方？？？
4. flex-wrap：压缩后使用
   1. wrap随窗口大小，可以换行，有行距
   2. nowrap默认
   3. wrap-reverse从左下开始，可以换行，有行距
5. align-content
   1. flex-start可以换行，无行距
   2. flex-end
   3. center
   4. space-evenly
   5. space-between
6. column-gap：列间隙，如1em
7. row-gap：行间隙
8. align-self：可应用单个元素
   1. start默认，顶端对齐
   2. center居中对齐
   3. end
9. order：改变元素的顺序
10. order:1;排名第一的放最后

    - -1放在开头第一位

```
<div class="container">
    <div class="box" id="box1">1</div>
    <div class="box" id="box2">2</div>
    <div class="box" id="box3">3</div>
    <div class="box" id="box4">4</div>
</div>
```

```
.container{
    display: flex;
    border: 10px solid black;
    height: 90vh;
}
.box{
    font-size: 8em;
    width: 150px;
    height: 150px;
    text-align: center;
    border-radius: 15px;
}
#box1{
    background-color: hsl(0, 100%, 70%);
    order:1;
}
#box2{
    background-color: hsl(75, 100%, 70%);
}
#box3{
    background-color: hsl(142, 100%, 70%);
}
#box4{
    background-color: hsl(184, 100%, 70%);
}
```

# 模糊

backdrop-filter: blur(5px);

## 雾化玻璃效果

```
backdrop-filter: blur(5px);
background-color: hsla(0, 0%, 100%, 0.1);
width: 100%;
```

# 交互式图像库

点击图片后进入图像展示放大

```
<div class="gallery">
    <a target="_blank" href="images/pizza.jpg">
        <img src="images/pizza.jpg">
    </a>
    <div class="description">Pizzas</div>
</div>
```

```
.gallery{
    border:1px solid hsl(0, 0%, 60%);
    display: inline-block;
    margin: 5px;
    width: 200px;
}
.gallery .description{
    padding: 10px;
    text-align: center;
}
.gallery:hover{
    border:1px solid hsl(0, 0%, 25%);
}
.gallery img{
    width: 100%;
    height: auto;
}
```

# 转换

要放在<div>里

> 1. translateX(50px)：左右移动，负数左移
>    - 括号内若是百分号，移动宽度的多少
> 2. translateY(50px)：上下移动
> 3. (x,y)：上下左右移动
> 4. rotateX(45deg)：绕x轴旋转，90°时看不见
> 5. rotateY绕y轴旋转，90°时看不见
> 6. rotateZ平面内旋转
> 7. scaleX(3);横向拉长（比例x，缩小为0.几
> 8. scaleY(3);竖向拉长（比例y
> 9. scale等倍放大
> 10. skewX向x轴倾斜（？？<90左斜，>90右斜）
> 11. matrix矩阵   （比例x，倾斜y，倾斜x，比例y，平移x，平移y）

```
#box1{
    width:250px;
    border:2px solid;
    height:150px;
    text-align: center;
    font-size:100px;
    background-color: chartreuse;

    transform: translateX(50px);
    transform: translateY(50px);
    transform: translate(50px,50px);
    transform: rotateX(180deg);
    transform: rotateY(180deg);
    transform: rotateZ(180deg);
    transform: scaleX(3);
    transform: scaleY(3);
    transform: scale(3);
    transform: skewX(45deg);
    transform: skewY(45deg);
    transform: skew(20deg,20deg);
    transform: matrix(1, 0, 0, 1, 0, 0);
    transform: translateX(100%) rotateZ(90deg) scale(0.5);
}
```

# transition过渡动画

一个元素在不同状态之间:hover，:active切换的时候定义不同的过渡效果。比如在不同的伪元素之间切换，或者通过 JavaScript 实现的状态变化。

```
/* Apply to 1 property */
/* property name | duration */
transition: margin-right 4s;

/* property name | duration | delay */
transition: margin-right 4s 1s;

/* property name | duration | timing function */
transition: margin-right 4s ease-in-out;

/* property name | duration | timing function | delay */
transition: margin-right 4s ease-in-out 1s;

/* Apply to 2 properties */
transition:
  margin-right 4s,
  color 1s;

/* Apply to all changed properties */
transition: all 0.5s ease-out;

/* Global values */
transition: inherit;
transition: initial;
transition: unset;
```



# animation自定义动画

> 1. 必须有：animation指定哪个动画
>
> 2. 必须有：animation-duration动画持续时间
>
> 3. animation-iteration-count动画播放次数——1，2，infinite（无限播放）......
>
> 4. animation-play-state播放状态：running、paused
>
> 5. animation-delay延迟时间
>
> 6. animation-direction:
>
>    - normal
>    - reverse
>    - alternate来回
>    - alternate-reverse
>
> 7. animation-timing-function动画持续期间如何运行
>
>    - ease-in-out加速（由慢到快）
>
>    - ease-out减速（由快到慢）
>    - linear匀速
>    - steps(5)多少次卡顿式前进
>
> 8. animation: name duration timing-function delay iteration-count direction fill-mode;
>
> 9. 持续时间 持续函数(如何运行) 延迟 迭代次数 动画状态 动画名称

```
#box1{
	animation: mySlide;
	animation-duration: 5s;
}
```

```
@keyframes mySlide{
    from{margin-left: 100%;}
    to{margin-left:0%;}
}
```

```
@keyframes slideLeft{
    from{transform: translateX(100%)}
}
```

```
@keyframes slideRight{
	to{transform: translateX(300%)}
}
```

### 伪类：光标停留开始#box1:hover

### 鼠标一直点击开始#box1:active

## 动画旋转

```
#box1{
	animation: myRotate;
	animation-duration: 5s;
}
@keyframes myRotate{
    100%{transform: rotateX(360deg)}
    100%{transform: rotateY(360deg)}
    100%{transform: rotateZ(360deg)}
}
```

## 透明度

### 从有到无

```
@keyframes fade{
    50%{opacity: 0}
}
```

### 从无到有

```
#box{
    opacity: 0;
}
@keyframes fadeIn{
    100%{opacity: 1}
}
```

## 比例

```
@keyframes shrink{
    50%{transform: scale(0.5, 0.5);}
}
```

## 逐帧变换颜色

```
@keyframes colorChange{
	20%{background-color: aqua;}
    40%{background-color:grey;}
    60%{background-color: darksalmon;}
    80%{background-color: deeppink;}
}
```

## 边缘阴影放大

```
@keyframes glow{
    50%{box-shadow: 0px 0px 50px rgb(30, 19, 160);}
}
```

