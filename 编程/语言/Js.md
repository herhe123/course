# 基础

## 链接

css:在<head>里

```
<link rel="stylesheet" href="style.css"cjs:在body的最后一行
```

```
<script src="index.js"></script>
```

随机长文本：lorem

## 弹出窗口

```javascript
window.alert("")只提示
window.prompt("")可输入，有文字提示
```

## document.getELementById

```javascript
.textContent文本输出
.value获取<input>的值
.onclick = function(){}按钮点击后执行的操作
.checked单选框、复选框选择时
.innerHTML图形输出
```

## <input

可设置

1. 默认值value=1
2. 最小值min=1
3. 直接设置css input{}

## 类型

typeof

```
console.log(typeof firstName);
```

## 模板文字

```
`Your name is ${fullName}`
```

## 运算符

```
**平方
%余数
+=	-=	*=	/=	**=	%=
```

## 优先级

- 括号
- 指数
- 乘、除、模
- 加减

先算括号，再算**，最后算/

## 输入

1. window.prompt()
2. <input> + <button>

## 类型转换

```javascript
x = Number(x);//输入框转换，确定输入的是数字
y = String(y);
z = Boolean(z);
```

## Math公式

x = Math.round(x);四舍五入

> 1. round四舍五入
> 2. floor向下舍，取整
> 3. trunc向下舍，取整
> 4. ceil向上入，取整
> 5. x = Math.pow(x, 3);x的多少次幂
> 6. sqrt平方根
> 7. abs绝对值
> 8. maximum = Math.max(x, y, z);最大值
> 9. minimum = Math.min(x, y, z);最小值
> 10. Math.PI；3.1415926......
> 11. log自然对数，相当于ln x
> 12. sin正弦
> 13. cos余弦
> 14. tan正切
> 15. sign符号函数，负的输出-1，正的输出1

.toFixed()多少位精度

## 随机数

注意：

1. 倍数：==max-min+1==
2. .floor外面加上min

```
const min = 1;
const max = 6;
let randomNum;
randomNum = Math.floor(Math.random() * (max - min + 1)) + min;
```

## 单选

- <input>type="radio"
- 并列单选name值相同（name="card"）
- id设置为...Btn
- js中.checked

## 复选框

- type="checkbox"

## 三元运算符、ternary operator

条件 ? 成立时 : 不成立时；

```js
let isStudent = false;
let message = isStudent ? "是学生" : "不是学生"；
console.log(message);
```

### 打折

discount需要除以100

```javascript
let purchaseAmount = 99;
let discount = purchaseAmount >= 100 ? 10 : 0;//10%折扣
console.log(`You total is $${purshaseAmount - purchaseAmount * (discount / 100)})`
```

## switch

用在确定的值

switch(变量名){
	case 数值一：
		console.log("");
		break;
    default:
    	console.log("");
}

```
let day = 2;
switch(day){
    case 1:
        console.log("It is Monday");
        break;
    case 7:
        console.log("It is Sunday");
        break;
    default:
        console.log(`${day} is not a day`)
}
```

## 字符串

1. 字符串长度：.length

2. 某位索引的字母——.charAt(0)

3. 第一次出现某字符串的索引：.indexOf("o")

4. 最后一次出现某索引：.lastIndexOf("o")

5. 删除字符串前后的空格 .trim()

6. 全部大写 .toUpperCase()

7. 全部小写.toLowerCase()

8. 替换某个符号，左边：被替换掉的，右：新的.replaceAll("-", "/")

9. 重复出现多少次.repeat()

10. 是否以某个东西开头.startsWith(" ")
    - 双引号内是空格或字母

11. 是否以某个东西结尾.endsWith(" ")

12. 是否包含某个东西.includes(" ")

13. 在开头填充少的位数，左边需要的位数，右边少的位数在开头填充的方式.padStart(15, "0");==如时钟==

14. 在末尾填充少的位数.padEnd(15, "0")

## 提取字符串中的某部分(字符串切片)

### 前几位、后几位：slice中两个数字

.slice(0, 2);

​	第一位：从某个索引处开始

​	第二位：提取几个索引（若没有，直接到末尾）

```js
const fullName = "Bro Code";
let firstName = fullName.slice(0, 2);
console.log(firstName);//输出Br
```

slice(-2);

​	从末尾开始，提取多少的索引，//输出de

### 提取姓：从空格以后至结束

第一位包括

```
let fullName = "Bro Code";
let lastName;

lastName = fullName.slice(fullName.indexOf(" ") + 1);
```

### 提取名：某个索引至某个索引

第二位不包括

```
let firstName;

firstName = fullName.slice(0, fullName.indexOf(" "));
```

## 方法链接：连续调用方法

```
let username = window.prompt("Enter your username: ");
username = username.trim().charAt(0).toUpperCase() + username.trim().slice(1).toLowerCase();
console.log(username);
```

## 逻辑运算符

&&	||	！

```
==比较相等，只看值，不看数据类型
===严格相等，值和数据类型
！=
！==
```

## while循环

声明，先判断后循环

```
while(条件){
	循环体
}
```

## do-while

先循环，后判断

```
let username;
do{
	循环体
}while(条件)
console.log("");
```

## for循环

for(声明初始值; 条件; 递增或递减)

## break,continue

break在此中止

continue除了这个，后面继续执行

## 嵌套循环

弹出输入行、列；外面是行，里面是列；

i = 1时，先执行内循环

```html
<label id="myRectangle"></label>
```

```javascript
let rows = window.prompt('Enter # of rows');
let columns = window.prompt('Enter # of columns');
const myRectangle = document.getElementById("myRectangle");

for(let i = 1; i<= rows; i++){
    for(let j = 1; j <= columns; j++){
        myRectangle.innerHTML += j;
    }
    myRectangle.innerHTML += "<br>";
}
```

## 函数

```js
startPrograms();

function startPrograms(){
	let userName = "Bro";
	let age = 21;
	
	happyBirthday(userName, age);
}
//使用函数时可以重命名
function happyBirthday(a, b){
	console.log("Happy birthday dear", userName);
	console.log("You are", age, " years old!");
}
```

## return

```js
let width;
let height;
width = window.prompt("Enter width");
height = window.prompt("Enter height");

function getArea(width, height){
	return width * height;
}
let area = getArea(width, height);
console.log("The area is:", area);
```

# 数字格式化

.toLocaleString

```javascript
let myNum = 1234356.789
myNum = myNum.toLocaleString("en-US");
myNum = myNum.toLocaleString("hi-IN");
myNum = myNum.toLocaleString("de-DE");
myNum = myNum.toLocaleString("en-US", {style: "currency", currency: "USD"});
myNum = myNum.toLocaleString("hi-IN", {style: "currency", currency: "INR"});
myNum = myNum.toLocaleString("de-DE", {style: "currency", currency: "EUR"});
myNum = myNum.toLocaleString(undefined, {style: "percent"});//百分比
myNum = myNum.toLocaleString(undefined, {style: "unit", unit: "celsius"});
console.log(myNum);
```

# 变量作用域

同一范围，变量唯一

```javascript
//错误
let x = 1;
let x = 2;
```

不同范围，无命名冲突

```
function1();
function2();

function function1(){
	let x = 1;
	console.log(x);
}

function function2(){
	let x = 2;
	console.log(x);
}
```

## 函数看不到其他函数的内部

函数内声明，其他函数无法引用

```javascript
function1();//函数名字是function1
function2();//函数名字是function2
//结果无法输出
function function1(){
	let x = 1;
	console.log(y);
}

function function2(){
	let y = 2;
	console.log(x);
}
```

## 外部声明的任何变量，在函数作用域是全局的

全局变量（函数外声明）

```js
let x= 3;
function function1(){
	console.log(x);
}

function function2(){
	console.log(x);
}
```

## 两个变量同名，在不同的范围，使用局部的版本

没有局部变量时，才使用全局变量版本

局部变量和全局变量同名时，使用全局变量版本

```javascript
let x= 3;
function function1(){
	let x = 1;//显示函数里声明的版本
	console.log(x);
}

function function2(){
	let x = 2;
	console.log(x);
}
```

# 数组

1. 访问数组console.log(fruits[0]);

2. 更新数组fruits[0] = "coconut"

3. **添加元素fruits.push("lemon");**

4. 删除最后一个元素.pop();

5. 在开头添加元素.unshift("mango");

6. 删除开头元素.shift();

7. 数组的长度.length;

8. 找到某个值的索引,从0开始，负值（-1）意味没有

9. .indexOf("apple");（字符串类型里面加引号，数字类型不加引号）

## 遍历数组

for循环+数组[i]

```
//向前迭代数组
let prices = [5, 10, 15, 20, 25];

for(let i = 0 ; i < prices.length ; i++){
	console.log(prices[i]);
}
```

## 排序

```
.sort();//按字母正序
.sort().reverse;//按字母逆序
```

## 二维、三维数组

生成多维数组：声明多个数组，新的数组包含前几个数组的名称（没有引号）

改变某个元素，二维数组第一个是行，第二个列

第一行是零行，第一列是零列

先声明groceryList再更改元素

```js
let fruits = ["apples", "oranges", "bananas"];
let vegetables = ["carrots", "onions", "potatoes"];
let meats = ["eggs", "children", "fish"];

let groceryList = [fruits, vegetables, meats];//生成三维数组
groceryList[0][1] = "mangoes";

//显示三个数组
for(let list of groceryList){
    console.log(list);
}

//显示元素
for(let list of groceryList){
    for(let food of list){
        console.log(food);
    }
}
```

# 扩展运算符

==**将数组、字符串分散为单独的元素**==

```js
let numbers = [1, 2, 3, 4, 5, 6, 7, 8];
console.log(...numbers);
//直接显示1 2 3 4 5 6 7 8 9
let userName = "Bro Code";
console.log(...userName);
//显示 B r o C o d e
```

## 散的整合：join("中间要连接的符号")

需要先用扩展运算符？？

连接字符串

```js
let username = "Bro Code";
let letters = [...username].join("-");
//输出B-r-o- -C-o-d-e
```

## 找最大值

==数组无法直接分析元素==，需要先使用扩展运算符

```js
let numbers = [1, 2, 3, 4, 5, 6, 7, 8];
let maxium = Math.max(...numbers);
```

## 糅合两个数组的元素

.push(...数组名称)

```js
let fruits = ["apple", "orange", "banana"];
let vegetables = ["carrots", "celery", "potatoed"];
//方法一
fruits.push(...vegetables);
console.log(...fruits);
//方法二
let foods = [...fruits, ...vegetables];
//再额外添加
let foods = [...fruits, ...vegetables, "eggs", "milk"];
```

# ==rest parameters休息参数==

元素整合为数组

**将单个元素(food1,food2,...,foodn)捆绑为数组(foods)，接受任何数量的参数**

```js
function getFood(...foods){
    return foods;
}
const foods = getFood("pizza", "hamburger", "hotbog", "sushi", "ramen");
console.log(foods);
//返回 ['pizza', 'hamburger', 'hotbog', 'sushi', 'ramen']
```

### 数组的求和？？？遍历相加得结果

遍历数组每个元素并运算：for(let number of numbers){result += number;}

```js
function sum(...numbers){
    let result = 0;
    for(let number of numbers){
        result += number;
    }
    return result;
}
const total = sum(1, 2, 3, 4);
console.log(`Your total is $${total});
//输出10
```

### 数组的平均值

计算数量：.length

在最后的return中使用.length

```js
function getAverage(...numbers){
    let result = 0;
    for(let number of numbers){
        result += number;
    }
    return result / numbers.length;
}

const total = getAverage(1, 2, 3, 4);
console.log(total);
```

### 组合字符串

```js
function combineStrings(...strings){
    return strings.join(" ");
}
const fullName = combineStrings("Mr.", "Spongebob", "Squarepants", "III");
console.log(fullName);
```

# 回调

把一个函数当作参数，传递给另一个函数。处理异步操作，读取文件网络请求或操作

允许函数调用另一个函数

- 先声明函数，再总函数里调用形参+分函数

```javascript
// sum(2, 3, displayDom);
sum(2, 3, displayConsole);

function sum(x, y, callBack){
    let result = x + y;
    callBack(result);
}
function displayDom(output){
    document.getElementById("myLabel").innerHTML = output;
}
function displayConsole(output){
    console.log(output);
}
```

# forEach

为数组每个元素执行一次回调函数

element,index,array顺序不变

```js
let students = ["peter", "bob", "susan"];
students.forEach(capitalize);
students.forEach(print);
function capitalize(element, index, array){
    array[index] = element[0].toUpperCase() + element.substring(1);
}

function print(element){
    console.log(element);
}
console.log(students[0]);
```

# map：返回新数组

对数组的元素执行一次回调函数，并创建**新的数组**

```js
将平方数变成一个新的数组
let numbers = [1, 2, 3, 4, 5];
//错误：numbers.map(squares);
let squares = numbers.map(square);
squares.forEach(print);

function square(element){
    return Math.pow(element, 2);
}
function print(element){
    console.log(element);
}
```

# filter

根据条件过滤某些元素，并创建一个新数组

```js
let ages = [18, 16, 21, 15, 40];
let adults = ages.filter(checkAge);

adults.forEach(print);

function checkAge(element){
    return element >= 18;
}
function print(element){
    console.log(element);
}
```

# reduce

- 将数组缩减为单个值，用于总结系列值并创建一个总数

- total累计值

```
let prices = [18, 16, 21, 15, 40];
let total = prices.reduce(checkOut);

console.log(`The total is: $${total}`);

function checkOut(total, element){
    return total + element;
}
```

# 数组元素排序

```javascript
let grades = [18, 16, 21, 70, 40];

grades = grades.sort(descendingSort);
grades.forEach(print);

function descendingSort(x, y){//降序
    return y - x;
}
function ascendingSort(x, y){//降序
    return x - y;
}
function print(element){
    console.log(element);
}
```



# 函数表达式

避免用随机函数名称污染全局范围

- function 后面没有函数名，函数名以变量名方式声明

```js
const greeting = function(){
    console.log("Hello!");
}
greeting();
```

```js
let count = 0;
const myLabel = document.getElementById("myLabel");

document.getElementById("decreaseButton").onclick = function(){
    count -= 1;
    myLabel.innerHTML = count;
}
document.getElementById("increaseButton").onclick = function(){
    count += 1;
    myLabel.innerHTML = count;
}
```

# 箭头函数表达式

去掉return

```js
const greeting = username => console.log(`Hello ${username}`);

greeting("Bro");
```

```js
const percent = (x, y) => x / y * 100;

console.log(`${percent(80, 100)}%`);
```

## 箭头+排序

```js
let grades = [18, 16, 21, 70, 40];

grades.sort((x, y) => y - x);
grades.forEach(element => console.log(element));
```

# 洗牌数组元素

```javascript
let cards = ["A", "2", "3", "4", "5", "6", "7", "8", "9", "10", "J", "Q", "K"];
shuffle(cards);

// console.log(cards);
cards.forEach(card => console.log(card));

function shuffle(array){
    let currentIndex = array.length;

    while(currentIndex != 0){
        let randomIndex = Math.floor(Math.random() * array.length);
        currentIndex -= 1;

        let temp = array[currentIndex];
        array[currentIndex] = array[randomIndex];
        array[randomIndex] = temp;
    }
    return array;
}
```

# 嵌套函数

用于闭包

```js
let userName = "Bro";
let userInbox = 0;

login();

function login(){
    displayUserName();
    displayUserInbox();

    function displayUserName(){
        console.log(`Welcome ${userName}`);
    }
    function displayUserInbox(){
        console.log(`You have ${userInbox} new messages`);
    }
}
```

# 闭包

```html
<button id="loginButton">login</button>
```

```js
document.getElementById("loginButton").onclick = login();

userInbox = 7321;

function login(){
    let userName = "Bro";
    let userInbox = 1;
    function alertUser(){
        alert(`${userName} have ${userInbox} new messages`);
        userInbox = 0;
    }
    return alertUser;
}
```

# map

包含任何数据类型的键值对的对象

- +=	.get添加到新的变量中
- .set添加键值对
- .delete删除键值对
- .has是否有某键值对
- .size键值对个数

```js
const store = new Map([
    ["t-shirt", 20],
    ["jeans", 30],
    ["socks", 10],
    ["underwear", 50]
]);

let shoppingCart = 0;

shoppingCart += store.get("t-shirt");//添加至结算列表
shoppingCart += store.get("jeans");

store.set("hat", 40);//添加到原始对象
store.delete("hat");//从对象中删除
console.log(store.has("underwear"));//检查对象中是否有
console.log(store.size);//键值对数量

console.log(shoppingCart);

store.forEach((value, key) => console.log(`${key}  $${value}`));
```

# 对象

```js
const car1 = {
    model: "Mustang",
    color: "red",
    year: 2023,
    
    drive : function(){
        console.log("You drive the car");
    },
    brake : function(){
        console.log("You step on the brakes");
    }
}
const car2 = {
    model: "Covette",
    color: "blue",
    year: 2024,
    
    drive : function(){
        console.log("You drive the car");
    }
}
console.log(car1.model);
car2.drive();
```

# this

对特定对象的引用

```js
const car1 = {
    model: "Mustang",
    
    drive : function(){
        console.log(`You drive the ${this.model}`);
    }
}
car1.drive();
```

对象外引用指window

```js
this.name = "myCoolWindow";
console.log(this.name);
```

# class

定义某一类型对象具有的属性和方法

```js
class Player{
    score = 0;

    pause(){
        console.log("You caused the game");
    }
    exit(){
        console.log("You exited the game");
    }
}
const player1 = new Player();
const player2 = new Player();

player1.score += 1;

console.log(player1.score);
console.log(player2.score);
```

# 构造函数

```js
class Student{
    constructor(name, age, gpa){
        this.name = name;
        this.age = age;
        this.gpa = gpa;
    }
    study(){
        console.log(`${this.name} is studying`);
    }
}
const student1 = new Student("Bob", 23, 4.0);
const student2 = new Student("Peter", 12, 3.7);

console.log(student1.name);
student1.study();

console.log(student2.gpa);
student2.study();
```

# static静态

属于class，而不是对象

static调用静态方法

```js
class Car{

    static numberOfCars = 0;

    constructor(model){
        this.model = model;
        Car.numberOfCars += 1;
    }

    static startRace(){
        console.log("3...2...1...GO");
    }
}
const car1 = new Car("Mustang");
const car2 = new Car("Corvette");
console.log(Car.numberOfCars);
Car.startRace();
```

# inheritance

子类可以从另一个类继承全部方法和属性

```js
class Animal{
    alive = true;
    eat(){
        console.log(`This ${this.name} is eating`);
    }
    sleep(){
        console.log(`This ${this.name} is sleeping`);
    }
}
class Rabbit extends Animal{
    name = "rabbit";
    run(){
        console.log(`This ${this.name} is running`);
    }
}
class Fish extends Animal{
    name = "fish";
    swim(){
        console.log(`This ${this.name} is swimming`);
    }
}
const rabbit = new Rabbit();
const fish = new Fish();
console.log(rabbit.alive);
rabbit.eat();
fish.sleep();
fish.swim();
```

# super

调用父类的构造函数

```js
class Animal{
    constructor(name, age){
        this.name = name;
        this.age = age;
    }
}
class Rabbit extends Animal{
    constructor(name, age, runnspeed){
        super(name, age);
        this.runnspeed = runnspeed;
    }    
}
class Fish extends Animal{
    constructor(name, age, swimmspeed){
        super(name, age);
        this.swimmspeed = swimmspeed;
    }    
}
const rabbit = new Rabbit("rabbit", 1, 40);
const fish = new Fish("fish", 2, 15);
console.log(rabbit.name);
console.log(fish.swimmspeed);
```

# getter	setter

get:访问属性时把对象绑定到函数，增加数据安全性

set:将对象的一个属性绑定到函数

```js
class Car{
    constructor(power){
        this._gas = 25;
        this._power = power;
    }
    get power(){
        return `${this._power}hp`;
    }
    get gas(){
        return `${this._gas}L (${this._gas / 50 * 100}%)`;
    }
    set gas(value){
        if(value > 50){
            value = 50;
        }
        else if(value < 0){
            value = 0;
        }
        this._gas = value;
    }
}
let car = new Car(400);
car.gas = 999950000;
console.log(car.power);
console.log(car.gas);
```

# object&argument

对象作为参数传递给函数

```js
class Car{
    constructor(model, year, color){
        this.model = model;
        this.year = year;
        this.color = color;
    }
}
const car1 = new Car("Mustang", 2023, "yellow");
const car2 = new Car("Corvette", 2024, "red");


changeColor(car2, "gold");
displayInfo(car2);

function displayInfo(car){
    console.log(car.model);
    console.log(car.year);
    console.log(car.color);
}
function changeColor(car, color){
    car.color = color;
}
```

# 对象数组

```js
class Car{
    constructor(model, year, color){
        this.model = model;
        this.year = year;
        this.color = color;
    }
    drive(){
        console.log(`You drive the ${this.model}`);
    }
}
const car1 = new Car("Mustang", 2023, "red");
const car2 = new Car("Lambo", 2024, "yellow");

const cars = [car1, car2];

// console.log(cars[0]);
// console.log(cars[1].year);
// cars[0].drive();

//创建一个数组，遍历数组的元素，访问所有属性、方法
startRace(cars);
function startRace(cars){
    for(const car of cars){
        car.drive();
    }
}
```

# 匿名对象

不用声明对象名称就可以创建对象，存储在数组中，无法直接访问匿名对象

优点：语法更少，减少代码大小，不用创建唯一的名称

```js
class Card{
    constructor(value, suit){
        this.value = value;
        this.suit = suit;
    }
}
let cards = [new Card("A", "Hearts"),
             new Card("A", "Spades"),
             new Card("A", "Diamonds"),
             new Card("A", "Clubs"),
             new Card("2", "Hearts"),
             new Card("2", "Spades"),
             new Card("2", "Diamonds"),
             new Card("2", "Clubs")];
// console.log(cards[0].value + cards[0].suit);
cards.forEach(card => console.log(`${card.value} ${card.suit}`));
```

# error handling

带有错误的描述对象

```js
try{
    let x = window.prompt("Enter a number");
    x = Number(x);

    if(isNaN(x)) throw "That wasn't a number";
    if(x == "") throw "That was empty";
    console.log(`${x} is a number`);
}
catch(error){
    console.log(error);
}
finally{
    console.log("That always executes");
}
```

# setTimeout

几毫秒后执行函数，异步函数不会暂停

```js
let item = "cryptocurrency";
let price = 420.69;

let timer1 = setTimeout(firstMessage, 3000, item, price);
let timer2 = setTimeout(secondMessage, 6000);
let timer3 = setTimeout(thirdMessage, 9000);

function firstMessage(item, price){
    alert(`Buy this ${item} for $${price}`);
}
function secondMessage(){
    alert(`This is not a scam!`);
}
function thirdMessage(){
    alert(`DO ITT!`);
}
document.getElementById("myButton").onclick = function(){
    clearTimeout(timer1);
    clearTimeout(timer2);
    clearTimeout(timer3);
    alert(`Thanks for buying <3!`);
}
```

# setInterval

在一个数字之后重复调用函数

```js
let count = 0;
let max = window.prompt("Count up to #");
max = Number(max);

let myTimer = setInterval(countup, 1000);

function countup(){
    count += 1;
    console.log(count);
    if(count >= max){
        clearInterval(myTimer);
    }
}
```

# data object日期

```js
let date = new Date();
// let date = new Date(0);//1970.1.1为标准，多少毫秒以后的时间
// let date = new Date(2023, 0, 1, 2, 3, 4, 5);//年份，月（从0至11），日，小时，分钟，秒，毫秒
// let date = new Date("January 1, 2023 00:00:00");//固定显示某个时间

date = date.toLocaleString();
document.getElementById("myLabel").innerHTML = date;
```

**只显示年或月或小时或分钟等**

```js
let date = new Date();

let year = date.getFullYear();
let dayOfMonth = date.getDate();
let dayOfWeek = date.getDay();
let month = date.getMonth();
let hour = date.getHours();
let minutes = date.getMinutes();
let seconds = date.getSeconds();
let ms = date.getMilliseconds();

date = date.toLocaleString();
document.getElementById("myLabel").innerHTML = year;
```

**改变日期中某个部分**

```js
let date = new Date();

date.setFullYear(2024);
date.setMonth(1);
date.setDate(31);
date.setHours(23);
date.setMinutes(1);
date.setSeconds(30);
date.setMilliseconds(0);

document.getElementById("myLabel").innerHTML = date;
```

**格式化日期表示形式**

```js
let date = new Date();
function formatDate(date){
    let year = date.getFullYear();
    let month = date.getMonth() + 1;
    let day = date.getDate();

    return `${month}/${day}/${year}`
}
function formatTime(date){
    let hours = date.getHours();
    let minutes = date.getMinutes();
    let seconds = date.getSeconds();
    let amOrpm = hours >= 12 ? "pm" : "am";
    hours = (hours % 12) || 12;

    return `${hours}:${minutes}:${seconds} ${amOrpm}`
}
date = date.toLocaleString();
document.getElementById("myLabel").innerHTML = formatTime(date);
```

# 异步代码

访问数据库、获取文件

现在开始，稍后某个时间结束。不会暂停程序，继续执行其他指令。

```
console.log("START");
setTimeout(() => console.log("This is asynchronous"), 5000);
console.log("END");
```

# console.time()

```js
console.time("Response time");
// alert("CLICK THE OK BUTTON");
setTimeout(() => console.log("HELLO"), 3000);

console.timeEnd("Response time");
```

# Promise

一个封装异步操作结果的对象

好处：让异步操作结果像同步一样返回

promise可以返回一个值或捕获异常

承诺在未来返回某些东西，处于等待状态，结果执行或被拒绝

```js
const promise = new Promise((resolve, reject) => {
    let fileLoaded = false;
    if(fileLoaded){
        resolve("File loaded");
    }
    else{
        reject("File NOT load");
    }
});
promise.then(value => console.log(value))
       .catch(error => console.log(error));
```

```js
const promise = new Promise(resolve => {
    setTimeout(resolve, 5000);
});
promise.then(() => console.log("Thanks for waiting!"));
```

```js
const wait = time => new Promise(resolve => {
    setTimeout(resolve, time);
});
wait(3000).then(() => console.log("Thanks for waiting!"));
```

# async

返回一个承诺

```js
//生产代码
async function loadFile(){
    let fileLoaded = true;

    if(fileLoaded){
        return "File loaded";
    }
    else{
        return "File NOT load";
    }
}
//消费代码
loadFile().then(value => console.log(value))
          .catch(error => console.log(error));
```

正常promise的做法

```js
function loadFile(){
    let fileLoaded = false;
    if(fileLoaded){
        return Promise.resolve("File loaded");
    }
    else{
        return Promise.resolve("File NOT load");
    }
}
promise.then(value => console.log(value))
       .catch(error => console.log(error));
```

# await

让函数等待承诺

```js
async function loadFile(){
    let fileLoaded = false;

    if(fileLoaded){
        return "File loaded";
    }
    else{
        throw "File NOT loaded";
    }
}
async function display(){
    try{
        document.getElementById("myH1").innerHTML = await loadFile();
    }
    catch(error){
        document.getElementById("myH1").innerHTML = error;
    }
}
display();
```

```js
async function loadFile(){
    const promise = new Promise((resolve, reject) => {
        let fileLoaded = true;

        if(fileLoaded){
            resolve("File loaded");
        }
        else{
            reject("File NOT loaded");
        }
    })
    try{
        document.getElementById("myH1").innerHTML = await promise;
    }
    catch(error){
        document.getElementById("myH1").innerHTML = error;
    }
}
loadFile();
```

# ES6 Modules

```html
<script type="module" src="index.js"></script>
```

math_util.js

```js
export const PI = 3.1415926;
export function getCircumfercence(radius){
    return 2 * PI * radius;
}
export function getArea(radius){
    return PI * radius * radius;
}
```

index.js

```js
import {PI, getCircumfercence, getArea} from "./math_util.js";
console.log(PI);

let circumference = getCircumfercence(10);
console.log(circumference);

let area = getArea(10);
console.log(area);
```

```js
import * as MathUtil from "./math_util.js";
console.log(MathUtil.PI);

let circumference = MathUtil.getCircumfercence(10);
console.log(circumference);

let area = MathUtil.getArea(10);
console.log(area);
```

# DOM

一个应用程序编程接口，更改页面内容的接口，无需重复加载页面反应更改

```js
console.log(document.title);
console.log(document.URL);

document.title = "Title goes here";
document.location = "https://cn.bing.com/";
document.body.style.backgroundColor = "pink";
document.getElementById("myDiv").innerHTML = "Hello";
```

# element electors

按名称获取元素

```html
<h1 id="myH1">标题一</h1>

<input type="radio" name="fruits" value="orange">
<label for="orange">orange</label><br>
<input type="radio" name="fruits" value="apple" checked="checked">
<label for="apple">apple</label><br>
<input type="radio" name="fruits" value="banana">
<label for="banana">banana</label><br>
```

```js
let element = document.getElementById("myH1");
element.style.backgroundColor = "yellow";
let fruits = document.getElementsByName("fruits");
// console.log(fruits[0]);
fruits.forEach(fruit => {
    if(fruit.checked){
        console.log(fruit.value);
    }
})
```

通过标签名称获取元素标题

```html
<ul>
    <li>carrots</li>
    <li>potatoes</li>
    <li>onions</li>
</ul>
```

```js
let vegetables = document.getElementsByTagName("li");
vegetables[2].style.backgroundColor = "lightgreen";
```

```html
<div class="desserts">ice-cream</div>
<div class="desserts">cake</div>
<div class="desserts">pie</div>
```

```js
let desserts = document.getElementsByClassName("desserts");
desserts[1].style.backgroundColor = "lightyellow";
```

每类型的第一个元素添加属性

```js
let element = document.querySelector("#myH1");
let element = document.querySelector("li");
let element = document.querySelector("[for]");
let element = document.querySelector(".desserts");

element.style.backgroundColor = "lightgreen";
```

每类型所有元素添加属性

```js
let elements = document.querySelectorAll("[for]");
elements.forEach(element => {
    element.style.backgroundColor = "lightgreen";
})
```

# DOM traversal

不同的DOM遍历

```html
<ul id="fruit">
    <li>apple</li>
    <li>orange</li>
    <li>banana</li>
</ul>
<ul id="vegetables">
    <li>carrots</li>
    <li>potatoes</li>
    <li>onions</li>
</ul>
<ul id="dessert">
    <li>ice-cream</li>
    <li>cake</li>
    <li>pie</li>
</ul>
```

```js
let element = document.body;
let child = element.firstElementChild;
let child = element.lastElementChild;//body的最后一个child是<script>

child.style.backgroundColor = "lightgreen";
```

**父级元素是body**

```js
let element = document.querySelector("#vegetables");
let parent = element.parentElement;
parent.style.backgroundColor = "lightgreen";
```

**sibling**

```js
let element = document.querySelector("#vegetables");
let sibling = element.nextElementSibling;
let sibling = element.previousElementSibling;
sibling.style.backgroundColor = "lightgreen";
```

**child**

```js
let element = document.querySelector("#fruit");
// let child = element.firstElementChild;
let child = element.children[0];
child.style.backgroundColor = "lightgreen";
```

迭代数组，所有child

```js
let element = document.querySelector("#fruit");
let children = Array.from(element.children);
children.forEach(child => child.style.backgroundColor = "lightgreen");
```

# 添加更改html元素

- .innerHTML：容易受到XSS攻击
- .textContent：首选

```js
const nameTag = document.createElement("h1");
nameTag.innerHTML = "Bro";
document.body.append(nameTag);

const myList = document.querySelector("#fruit");
const listItem = document.createElement("li");
listItem.textContent = "mango";
// myList.append(listItem);
// myList.prepend(listItem);
myList.insertBefore(listItem, myList.getElementsByTagName("li")[2]);
```

# 添加、更改css属性

```html
<h1 id="myTitle">This is my title</h1>
```

```js
const title = document.getElementById("myTitle");
title.style.backgroundColor = "#222222";
title.style.color = "rgb(50, 200, 250)";
title.style.fontFamily = "consolas";
title.style.textAlign = "center";
title.style.border = "2px solid";
title.style.display = "block";
```

# 事件

**.onclick**

```html
<button id="myButton" onclick="doSomething()">button</button>
```

```js
const element = document.getElementById("myButton");
element.onclick = doSomething;//不要调用，相当于一个回调
function doSomething(){
    alert("You did something");
}
```

**.onload**

```html
<body onload = "doSomething()">
    <button id="myButton">button</button>
```

```js
const element = document.body;
element.onload = doSomething;//加载属性
```

**.onchange**

```html
<button id="myButton">button</button>
<input id="myText">
```

```js
const element = document.getElementById("myText");
element.onchange = doSomething;
```

**div**

```html
<div id="myDiv"></div>
```

```css
#myDiv{
    background-color: lightgreen;
    width: 100px;
    height: 100px;
}
```

```js
element.onmouseover = doSomething;//鼠标悬停
element.onmouseout = doSomethingElse;//鼠标移出
element.onmousedown = doSomething;//鼠标点下
element.onmouseup = doSomethingElse;//鼠标松开
```

# 事件侦听器.addEventListener

```html
    <div id="outerDiv">
    <div id="innerDiv"></div>
</div>
```

```css
#innerDiv{
    background-color: lightgreen;
    width: 100px;
    height: 100px;
    border: 1px solid;
}
#outerDiv{
    background-color: lightgreen;
    width: 200px;
    height: 200px;
}
```

```js
const innerDiv = document.getElementById("innerDiv");
innerDiv.addEventListener("mouseover", changeRed);
innerDiv.addEventListener("mouseout", changeGreen);
function changeRed(){
    innerDiv.style.backgroundColor = "red";
}
function changeGreen(){
    innerDiv.style.backgroundColor = "lightgreen";
}
```

```js
const innerDiv = document.getElementById("innerDiv");
const outerDiv = document.getElementById("outerDiv");
innerDiv.addEventListener("click", changeBlue);//无true先处理内层
outerDiv.addEventListener("click", changeBlue, true);//添加true后先处理外层

function changeBlue(){
    alert(`You selected ${this.id}`);
    this.style.backgroundColor = "lightblue";
}
```

# 显示、隐藏html元素

display	->	visibility

none		->	hidden

block		->	visible

```html
<button id="myBtn">toggle</button>
<img id="myImg" src="car.jpg" style="display: none;">
<p>Press the button...</p>
```

```js
const myBtn = document.querySelector("#myBtn");
const myImg = document.querySelector("#myImg");
myBtn.addEventListener("click", () => {
    if(myImg.style.display == "none"){
        myImg.style.display = "block";
    }
    else{
        myImg.style.display = "none";
    }
}) 
```

# 检测按键

```js
window.addEventListener("keydown", event => console.log(event.key));
```

```css
#myDiv{
    width: 100px;
    height: 100px;
    border: 1px solid;
    background-color: lightgreen;
    position: relative;
}
```

```js
const myDiv = document.getElementById("myDiv");
// window.addEventListener("keydown", move);
window.addEventListener("keyup", move);
let x = 0;
let y = 0;
function move(event){
    switch(event.key){
        case "ArrowDown":
            y += 5;
            myDiv.style.top = y + "px";
            break;
        case "ArrowUp":
            y -= 5;
            myDiv.style.top = y + "px";
            break;
        case "ArrowRight":
            x += 5;
            myDiv.style.left = x + "px";
            break;
        case "ArrowLeft":
            x -= 5;
            myDiv.style.left = x + "px";
            break;
        default:
            break;
    }
}
```

# 动画

```js
const myButton = document.getElementById("myButton");
const myAnimation = document.getElementById("myDiv");

myButton.addEventListener("click", begin);
function begin(){
    let timerId = null;
    let x = 0;
    let y = 0;
    let degrees = 0;//旋转
    let scaleX = 1;//比例
    let scaleY = 1;//比例

    timerId = setInterval(frame, 5);
    function frame(){
        if(x >= 200 || y >= 200){
            clearInterval(timerId);
        }
        if(scaleY >= 3){//比例
            clearInterval(timerId);
        }
        else{
            degrees += 1;//旋转
            x += 1;
            y += 1;
            myAnimation.style.top = x + "px";
            myAnimation.style.left = y + "px";
            myAnimation.style.transform = "rotateY("+degrees+"deg)";//为什么里面两个加号
        }
        else{
            scaleY += 0.01;
            myAnimation.style.transform = "scale("+scaleX+","+scaleY+")";
        }//比例
    }
}
```

# canvas API

放在<body>里，在html里声明height、width，若在css声明，则js中无法使用

```html
<canvas id="myCanvas" height="500" width="500"></canvas>
```

**画线**

```js
let canvas = document.getElementById("myCanvas");
let context = canvas.getContext("2d");

//画线
context.strokeStyle = "lightgreen";//线条颜色
context.lineWidth = 5;
context.beginPath();//开始
context.moveTo(0, 0);
context.lineTo(250, 250);
context.lineTo(250, 500);
context.moveTo(500, 0);
context.lineTo(250, 250);
context.stroke();//结束
```

**画三角形，填充**

```js
context.strokeStyle = "grey";
context.fillStyle = "yellow";
context.lineWidth = 5;
context.beginPath();
context.moveTo(250, 0);
context.lineTo(0, 250);
context.lineTo(500, 250);
context.lineTo(250, 0);
context.stroke();//填充颜色时有边框
context.fill();//填充颜色
```

**矩形**

```js
context.lineWidth = "2";
context.fillStyle = "red";//填充的颜色
context.fillRect(0, 0, 250, 250);//填充矩形
context.strokeStyle = "black";//边框颜色
context.strokeRect(0, 0, 250, 250);//画矩形

context.fillStyle = "yellow";
context.fillRect(250, 250, 250, 250);
context.strokeStyle = "black";
context.strokeRect(250, 250, 250, 250);
```

**圆**

.arc(x, y, 半径，起始角度，结束角度，是否反转)

反转后面加true，否则没有

```js
context.lineWidth = "5";
context.fillStyle = "lightgreen";
context.strokeStyle = "green";
context.beginPath();
context.arc(250, 250, 200, 0, 2 * Math.PI);
context.stroke();
context.fill();
```

**文本**

```js
context.font = "50px MV Boli";
context.fillStyle = "grey";
context.textAlign = "center";
context.fillText("You Win", canvas.width / 2, canvas.height / 2);
```

# window

```js
console.dir(window);//打印window对象
console.log(window.innerWidth);
console.log(window.innerHeight);
console.log(window.outerWidth);
console.log(window.outerHeight);
console.log(window.scrollX);//滚动x
console.log(window.scrollY);//滚动y
```

```js
console.log(window.location.href);
window.location.href = "https://www.baidu.com/";
console.log(window.location.hostname);
console.log(window.location.pathname);
```

```js
const myButton = document.querySelector("#myButton");
myButton.addEventListener("click", () => window.open());
myButton.addEventListener("click", () => window.close());
myButton.addEventListener("click", () => window.print());
window.alert("Hello!");
window.confirm("Press OK to continue");
let age = window.prompt("Enter your age");
if(age < 18){
    window.alert("You must be 18+ to visit this site");
    window.close();
}
```

# cookie

```js
console.log(navigator.cookieEnabled);
```

```js
document.cookie = "firstName=Smith; expires=Sun 25 March 2024 12:00:00 UTC; path=/";
document.cookie = "lastName=Patrick; expires=Sun 25 March 2024 12:00:00 UTC; path=/";
console.log(document.cookie);
```

```js
setCookie("firstName", "SpongeBob", 365);
setCookie("lastName", "SquarePants", 365);
console.log(getCookie("firstName"));
console.log(getCookie("lastName"));
// console.log(document.cookie);
// deleteCookie("email");
function setCookie(name, value, daysToLive){
    const date = new Date();
    date.setTime(date.getTime() + (daysToLive * 24 * 60 * 60 * 1000));
    let expires = "expires=" + date.toUTCString();
    document.cookie = `${name}=${value}; ${expires}; path=/`;
}
function deleteCookie(name){
    setCookie(name, null, null);
}
function getCookie(name){
    const cDecoded = decodeURIComponent(document.cookie);
    const cArray = cDecoded.split("; ");
    let result = null;
    cArray.forEach(element => {
        if(element.indexOf(name) == 0){
            result = element.substring(name.length + 1)
        }
    })
    return result;
}
```

```html
<label for="firstText">first name:</label>
<input id="firstText"><br>
<label for="lastText">last name:</label>
<input id="lastText"><br>
<button id="submitBtn">submit</button>
<button id="cookieBtn">get cookies</button>
```

```js
const firstText = document.querySelector("#firstText");
const lastText = document.querySelector("#lastText");
const submitBtn = document.querySelector("#submitBtn");
const cookieBtn = document.querySelector("#cookieBtn");

submitBtn.addEventListener("click", () => {
    setCookie("firstName", firstText.value, 365);
    setCookie("lastName", lastText.value, 365);
});
cookieBtn.addEventListener("click", () => {
    firstText.value = getCookie("firstName");
    lastText.value = getCookie("lastName");
});

deleteCookie("firstName");
deleteCookie("lastName");
```

# 例：计数器

==文本对齐：==
先设置display：block；
再设置text-align: center;

所有button放在一个<div>里

id用#

在id里设置文本对齐，不能在class里？？

```
const decreaseBtn = document.getElementById("decreaseBtn");
const resetBtn = document.getElementById("resetBtn");
const increaseBtn = document.getElementById("increaseBtn");
const countLabel = document.getElementById("countLabel");
let count = 0;
decreaseBtn.onclick = function(){
    count--;
    countLabel.textContent = count;
}
resetBtn.onclick = function(){
    count = 0;
    countLabel.textContent = count;
}
increaseBtn.onclick = function(){
    count++;
    countLabel.textContent = count;
}
```



# 例：猜数字

设置最大值、最小值
设置尝试次数，初始为0
设置运行状态
不是数字、不在范围内不计次数
猜测值在while循环中设置
判断数字if(isNaN(guess))
猜对的else里running=false

```js
const minNum = 1;
const maxNum = 100;
const answer = Math.floor(Math.random() * (maxNum - minNum + 1)) + minNum;

let attempts = 0;
let guess;
let isRunning = true;

while(isRunning){
    guess = window.prompt(`Guess a number between ${minNum} - ${maxNum}`);
    guess = Number(guess);

    if(isNaN(guess)){
        window.alert("Please enter a valid number");
    }
    else if(guess < minNum || guess > maxNum){
        window.alert("Please enter a valid number");
    }
    else{
        attempts++;
        if(guess < answer){
            window.alert("Too Low");
        }
        else if(guess > answer){
            window.alert("Too Big");
        }
        else{
            window.alert(`Right! You have use ${attempts} attempts`);
            isRunning = false;
        }
    }
}
```

# ==例：转换温度==

## html

放在<form>里
标题在<h1>里
增加默认值，value=0；数值input的id设置为textBox
相同name设置为unit
选项后增加<label for="">
button设置onclick="convert()"
最后结果设置为<p>
摄氏度符号：按住alt，小键盘输入0176°

```html
<form>
    <h1>Temperature conversion: </h1>
    <input type="number" id="textBox" value="0"><br>

    <input type="radio" id="toFahrenheit" name="unit">
    <label for="toFahrenheit">Celsius -> Fahrenheit</label>

    <input type="radio" id="toCelsius" name="unit">
    <label for="toCelsius">Fahrenheit -> Celsius</label>

    <button type="button" onclick="convert()">submit</button>
    <p id="result">Select a unit</p>
</form>
```

## css

```
body{
    font-family: Arial, sans-serif;
    background-color: hsl(0, 0%, 95%);
}
form{
    text-align: center;
    margin: auto;
    max-width: 350px;
    padding: 25px;
    border-radius: 10px;
    background-color: hsl(0, 0%, 100%);
    box-shadow: 5px 5px 15px hsla(0, 0%, 0%, 0.3);
}
h1{
    color: hsl(223, 100%, 64%);
}
#textBox{
    width: 50%;
    text-align: center;
    font-size: 2em;
    border: 2px solid hsla(0, 0%, 0%, 0.8);
    border-radius: 4px;
    margin-bottom: 15px;
}
label{
    font-size: 1.5em;
    font-weight: bold;
}
button{
    background-color: hsl(0, 100%, 60%);
    margin-top: 15px;
    border-color: white;
    font-size: 1.5em;
    color: white;
    padding: 10px 15px;
    border-radius: 5px;
    cursor: pointer;
}
button:hover{
    background-color: hsl(0, 100%, 50%);
}
#result{
    font-size: 1.75em;
    font-size: bold;
}
```

## js

function convert(){}
设置未选择时的选项在else中
.toFixed(数字)有多少位精度
textContent的结果输出用字符串连接，不用模板文字
<input>取值时加Number()

- 摄氏度Celsius：转华氏F = C * 9 / 5 + 32；
- 华氏度Fahrenheit：转摄氏C = (F - 32) * (5 / 9);

```javascript
const textBox = document.getElementById("textBox")
const toFahrenheit = document.getElementById("toFahrenheit");
const toCelsius = document.getElementById("toCelsius");
const result = document.getElementById("result");

function convert(){

    if(toFahrenheit.checked){
        temp = Number(textBox.value);
        temp = temp * 9 / 5 + 32;
        result.textContent = temp.toFixed(1) + "°F";
    }
    else if(toCelsius.checked){
        temp = Number(textBox.value);
        temp = (temp - 32) * (5 / 9);
        result.textContent = temp.toFixed(1) + "°C";
    }
    else{
        result.textContent = "Select a unit";
    }
}
```

# ==例：掷骰子==

## html

放在<div>里（为什么不放在<form>里）

```html
<div id="container">
    <h1>Dice Roller</label>
    <label># of dice:</label>
    <input type="number" value="1" id="numOfDice" min="1">
    <button onclick="rollDice()">Roll Dice</button>
    <div id="diceResult"></div>
    <div id="diceImages"></div>
</div>
```

## css

```css
#container{
    text-align: center;
    font-size: 2rem;
    font-weight: bold;
    font-family: Arial, sans-serif;
}
button{
    font-size: 1.5rem;
    padding: 10px 15px;
    background-color:hsl(200, 60%, 50%);
    color: white;
    border-radius: 5px;
    border: none;
    cursor: pointer;
}
button:hover{
    background-color:hsl(200, 60%, 60%);
}
button:active{
    background-color:hsl(200, 60%, 70%);
}
input{
    font-size: 2rem;
    text-align: center;
    width: 150px;
    font-weight: bold;
}
#diceResult{
    margin: 25px;
}
#diceImages img{
    width: 150px;
    margin: 50px;
}
```

## js

```javascript
//随机数、图像引用
function rollDice(){
    const numOfDice = document.getElementById("numOfDice").value;
    const diceResult = document.getElementById("diceResult");
    const diceImages = document.getElementById("diceImages");
    const values = [];
    const images = [];

    for(let i = 1; i <= numOfDice; i++){
        const value = Math.floor(Math.random() * 6) + 1;
        values.push(value);
        images.push(`<img src="${value}.png" alt="Dice ${value}">`);
        diceResult.textContent = `dice:${values.join(', ')}`;
        diceImages.innerHTML = images.join('');
    }
}
```

# 例：随机密码生成器

对各个字符的取值在函数中声明列出
声明允许字符为空
声明密码为空
三元运算符确定允许字符
for循环中声明随即索引，通过递增逐步形成密码
for循环外，函数体内返回密码

```js
function generatePassword(length, includeLowercase, includeUppercase, includeSymbols){
    const lowercaseChars = "abcdefghijklmnopqrstuvwxyz";
    const uppercaseChars = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
    const numberChars = "0123456789";
    const symbolChars = "!@#$%^&*()_-=+";

    let allowedChars = "";
    let password = "";

    allowedChars += includeLowercase ? lowercaseChars : "";
    allowedChars += includeUppercase ? uppercaseChars : "";
    allowedChars += includeNumbers ? numberChars : "";
    allowedChars += includeSymbols ? symbolChars : "";

    if(length <= 0){
        return '(password length must be at least 1)';
    }
    if(allowedChars.length === 0){
        return '(At least 1 set of character needs to be selected';
    }

    for(let i = 0; i < length; i++){
        const randomIndex = Math.floor(Math.random() * allowedChars.length);
        password += allowedChars[randomIndex];
    }
    return password;
}
const passwordLength = 12;
const includeLowercase = true;
const includeUppercase = true;
const includeNumbers = true;
const includeSymbols = true;

const password = generatePassword(passwordLength,
                                  includeLowercase,
                                  includeUppercase,
                                  includeNumbers,
                                  includeSymbols);
console.log(`Generated password: ${password}`);
```

# 例：当前时钟更新

## html

```html
<div id="clock-container">
    <div id="clock">00:00:00</div>
</div>
```

## css

```css
body{
    margin: 0;
    background-image: url(背景图.jpg);
    background-position: center;
    background-size: cover;
    background-attachment: fixed;
    background-repeat: no-repeat;
}
#clock-container{
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100vh;
}
#clock{
    font-family: monospace;
    font-size: 6.5rem;
    font-weight: bold;
    text-align: center;
    color:white;
    backdrop-filter: blur(5px);
    background-color: hsla(0, 0%, 100%, 0.1);/*雾化玻璃状*/
    width: 100%;
}
```

## js
toString()转化为字符串
用的是setInterval

```js
function updateClock(){
    const now = new Date();
    let hours = now.getHours();
    const meridiem = hours > 12 ? "PM" : "AM";
    hours = hours % 12 || 12;
    hours = hours.toString().padStart(2, 0);
    const minutes = now.getMinutes().toString().padStart(2, 0);
    const seconds = now.getSeconds().toString().padStart(2, 0);

    const timeString = `${hours}:${minutes}:${seconds} ${meridiem}`;
    document.getElementById("clock").textContent = timeString;
}
updateClock();
setInterval(updateClock, 1000);
```

# 例：秒表

```html
<div id="timeContainer">
    <div id="timeDisplay">00:00:00</div>
    <button id="startBtn" class="timerBtn">Start</button>
    <button id="pauseBtn" class="timerBtn">Pause</button>
    <button id="resetBtn" class="timerBtn">Reset</button>
</div>
```

```js
const timeDisplay = document.querySelector("#timeDisplay");
const startBtn = document.querySelector("#startBtn");
const pauseBtn = document.querySelector("#pauseBtn");
const resetBtn = document.querySelector("#resetBtn");

let startTime = 0;
let elapsedTime = 0;
let currentTime = 0;
let paused = true;
let intervalid;
let hrs = 0;
let mins = 0;
let secs = 0;

startBtn.addEventListener("click", () => {
    if(paused){
        paused = false;
        startTime = Date.now() - elapsedTime;
        intervalid = setInterval(updateTime, 75);
    }
});
pauseBtn.addEventListener("click", () => {
    if(!paused){
        paused = true;
        elapsedTime = Date.now() - startTime;
        clearInterval(intervalid);
    }
});
resetBtn.addEventListener("click", () => {
    paused = true;
    clearInterval(intervalid);
    startTime = 0;
    elapsedTime = 0;
    currentTime = 0;
    hrs = 0;
    mins = 0;
    secs = 0;
    timeDisplay.textContent = "00:00:00";
});

function updateTime(){
    elapsedTime = Date.now() - startTime;
    secs = Math.floor((elapsedTime / 1000) % 60);//毫秒变秒
    mins = Math.floor((elapsedTime / (1000 * 60)) % 60);
    hrs = Math.floor((elapsedTime / (1000 * 60 * 60)) % 60);

    secs = pad(secs);
    mins = pad(mins);
    hrs = pad(hrs);

    timeDisplay.textContent = `${hrs}:${mins}:${secs}`;

    function pad(unit){
        return (("0") + unit).length > 2 ? unit : '0' + unit;
    }
}
```

# 例：石头、剪刀、布

```html
    <div id="gameDiv">
        <h1 class="gameText" id="playerText">Player:</h1>
        <h1 class="gameText" id="computerText">Computer:</h1>
        <h1 class="gameText" id="resultText">Result:</h1>

        <button class="choiceBtn">ROCK</button>
        <button class="choiceBtn">PAPER</button>
        <button class="choiceBtn">SCISSORS</button>
    </div>
```

```js
const playerText = document.querySelector("#playerText");
const computerText = document.querySelector("#computerText");
const resultText = document.querySelector("#resultText");
const choiceBtns = document.querySelectorAll(".choiceBtn");
let player;
let computer;
let result;

choiceBtns.forEach(button => button.addEventListener("click", () => {
    player = button.textContent;
    computerTurn();
    playerText.textContent = `Player: ${player}`;
    computerText.textContent = `Computer: ${computer}`;
    resultText.textContent = checkWinner();
}));
function computerTurn(){
    const randomNum = Math.floor(Math.random() * 3) + 1;
    switch(randomNum){
        case 1:
            computer = "ROCK";
            break;
        case 2:
            computer = "PAPER";
            break;
        case 3:
            computer = "SCISSORS";
            break;
    }
}
function checkWinner(){
    if(player == computer){
        return "Draw!";
    }
    else if(computer == "ROCK"){
        return (player == "PAPER") ?  "You Win!" : "You Lose!";
    }
    else if(computer == "PAPER"){
        return (player == "SCISSORS") ? "You Win!" : "You Lose!";
    }
    else if(computer == "SCISSORS"){
        return (player == "ROCK") ? "You Win!" : "You Lose!";
    }
}
```

# 例：井字游戏

```html
<div id="gameContainer">
    <h1>Tic Tac Toe</h1>
    <div id="cellContainer">
        <div cellIndex="0" class="cell"></div>
        <div cellIndex="1" class="cell"></div>
        <div cellIndex="2" class="cell"></div>
        <div cellIndex="3" class="cell"></div>
        <div cellIndex="4" class="cell"></div>
        <div cellIndex="5" class="cell"></div>
        <div cellIndex="6" class="cell"></div>
        <div cellIndex="7" class="cell"></div>
        <div cellIndex="8" class="cell"></div>
    </div>
    <h2 id="statusText"></h2>
    <button id="restartBtn">Restart</button>
</div>
```

```css
.cell{
    width: 75px;
    height: 75px;
    border: 2px solid;
    box-shadow: 0 0 0 2px;
    line-height: 75px;
    font-size: 50px;
    cursor: pointer;
}
#gameContainer{
    font-family: "Permanent Marker", cursive;
    text-align: center;
}
#cellContainer{
    display: grid;
    grid-template-columns: repeat(3, auto);
    width: 225px;
    margin: auto;
}
```

```js
const cells =document.querySelectorAll(".cell");
const statusText = document.querySelector("#statusText");
const restartBtn = document.querySelector("#restartBtn");
const winConditions = [
    [0, 1, 2],
    [3, 4, 5],
    [6, 7, 8],
    [0, 3, 6],
    [1, 4, 7],
    [2, 5, 8],
    [0, 4, 8],
    [2, 4, 6]
];
let options = ["", "", "", "", "", "", "", "", ""];
let currentPlayer = "X";
let running = false;

intializeGame();

function intializeGame(){
    cells.forEach(cell => cell.addEventListener("click", cellClicked))
    restartBtn.addEventListener("click", restartGame);
    statusText.textContent = `${currentPlayer}'s turn`;
    running = true;
}
function cellClicked(){
    const cellIndex = this.getAttribute("cellIndex");
    if(options[cellIndex] != "" || !running){
        return;
    }
    updateCell(this, cellIndex);
    checkWinner();
}
function updateCell(cell, index){
    options[index] = currentPlayer;
    cell.textContent = currentPlayer;
}
function changePlayer(){
    currentPlayer = (currentPlayer == "X") ? "O" : "X";
    statusText.textContent = `${currentPlayer}'s turn`;
}
function checkWinner(){
    let roundWon = false;
    for(let i = 0; i < winConditions.length; i++){
        const condition = winConditions[i];
        const cellA = options[condition[0]];
        const cellB = options[condition[1]];
        const cellC = options[condition[2]];
        if(cellA == "" || cellB == "" || cellC == ""){
            continue;
        }
        if(cellA == cellB && cellB == cellC){
            roundWon = true;
            break;
        }
    }
    if(roundWon){
        statusText.textContent = `${currentPlayer} wins!`;
        running = false;
    }
    else if(!options.includes("")){
        statusText.textContent = `Draw!`;
        running = false;
    }
    else{
        changePlayer();
    }
}
function restartGame(){
    currentPlayer = "X";
    options = ["", "", "", "", "", "", "", "", ""];
    statusText.textContent = `${currentPlayer}'s turn`;
    cells.forEach(cell => cell.textContent = "");
    running = true;
}
```

# 例：贪吃蛇



# 常用css设置

## <body里统一设置

字体、背景颜色

## <form

text-align	max-width	margin:auto;	padding	border-radius	box-shadow

## <input

可不设置id，直接input{}
width:50%	text-align（有默认值时）	font-size:2rem	border: 2px solid hsla	border-radius:4px（可略）	margin-bottom:15px	加粗

## <label或其他出现字的时候

font-size	font-weight

## display

单个元素（一个label）：block

## 宽度

```css
max-width: 350px;
```

## 并列格式

### <div

1. 多个按钮时并列统一设置时，放在一个<div>里，id=btnContainer，统一设置对齐
2. 字体、字号、加粗

### <class

其他格式需要设置相同的class

## hsl颜色

百分比越小，颜色越深

点击、活跃：颜色变浅，百分比增大

## 常用的字体、字号

Verdana	Arial	Helvetica	sans-serif

em:100%

1.5em	3em	10em（大字号）	6.5rem（单独元素）

## radius

小框5px，大框10px

## 阴影

box-shadow: 5px 5px 15px hsla(0, 0%, 0%, 0.3)

## 按钮竖向高度

  line-height: 30px

## 按钮其他常见设置

**按钮字体大小单独调**1.5rem

padding:5px 25px	或	10px 20px	或10px 15px

cursor:pointer

transition: background-color 0.25s;

加粗	

# 常用HTML设置

相同级别的button，设置一个相同的class

