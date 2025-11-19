分支：if,swtich

循环：whlie for  do-while

#include 包含一个文件的内容

\n换行

```c
#include <stdio.h>
int main(){
    printf("I like pizza\n");
    printf("It's really good");
    return 0;
}
```

命令提示符运行C

更改位置：cd 源代码位置

读取：gcc 文件名.C

读取：a.exe

# 转义序列

\n新行

\t制表符，tab，可生成相当的间距

```
\"打印引号作为输出，单引号\'，反写杠\\
```

# 变量

## 格式说明符

### 单个字符放在单引号里！！！

### 字符串放在引号里

```
int表示整数
float浮点数（小数）
char单个字符，放在单引号里;字符串，变量后有[]
```

```c
int age = 21;			//%d整数
float c = 3.141592653589793;	//%f
double d = 3.141592653589793;	//%lf
char grade = 'C';		//%c字符
char name[] = "Bro";	//%s字符串、多个字符
printf("Hello %s\n", name);
printf("You are %d years old\n", age);
printf("You average grade is %c\n", grade);
printf("%f\n", c);//双精度
printf("%lf\n", d);//双精度
```

# 数据类型

- float：%f浮点数，4bytes，32bits，6到7个有效数字
- double：%lf双精度浮点数，8bytes，64bits，15到16个有效数字

```c
printf("%0.15lf\n", c);//浮点数，小数点后十五位,失去精度
printf("%0.15lf\n", d);//浮点数，小数点后十五位
```

- 布尔值bool：0假，1真，1bytes

```c
#include <stdbool.h>
bool e = true;//%d
```

- char :-128~127的整数，%d显示整数，%c转换为ASCII字符

- unsigned char：0~255无符号的字符，%d显示整数，%c转换为ASCII字符，超出255转换为0
- short int：int可省略，2bytes，-32768~32767，%d整数，溢出显示范围内最小（-32768）
- unsigned short int：2bytes，0~65535，%d整数，溢出显示范围内最小（0）
- int：4bytes，-20亿~20亿，%d
- unsigned int：4bytes, 0~40亿，%u
- long long int：8bytes, -9万亿~9万亿，%lld
- unsigned long long int : 8bytes, 0~18万亿，%llu, 声明时数字后面加U

# 格式化说明符

设置浮点数的输出小数精度%.2f ——两位小数

%1最小宽度空格数，右对齐

%-左对齐，后面留空格

```
%8.2f——8个空格，2为小数
%-8.2f
```

# 常量

const float PI = 前面加上const

# 算术运算符

## 除

结果y若存储在整数int中，只存储整数部分

```
int x = 5;
int y = 2;
int z = x / y;
printf("%d", z);
```

除数若为整数，存储为浮点数、双精度数

```
//method 1
int x = 5;
float y = 2;
float z = x / y;
printf("%f", z);
```

```
//method 2
int x = 5;
int y = 2;
float z = x / (float) y;
printf("%f", z);
```

## 模

```
int x = 5;
int y = 2;
int z = x % y;
printf("%d", z);
```

### 递增++，递减--

# 增强赋值运算符

+=	-=	/= 	%=

# 用户输入

- scanf读取到空格为止，需要&

  - scanf("格式说明符", &变量名)

- fgets(name, 25, stdin);可读取空格，使用回车时会包含换行符

  - 给name赋值，用户输入的大小为25，stdin标准输入

- strlen字符串长度函数

  ```
  #include <string.h>
  char name[25];
  int age;
  printf("\nWhat's your name?");
  fgets(name, 25, stdin);
  // scanf("%s", &name);
  name[strlen(name)-1] = '\0';
  
  printf("\nHow old are you?");
  scanf("%d", &age);
  ```

  

# 数学函数

```
#include <math.h>
double A = sqrt(9);
double B = pow(2, 4);
int C = round(3.14);
int D = ceil(3.14);
int E = floor(3.99);
double F = fabs(-100);
double G = log(3);
double H = sin(45);
double I = cos(45);
double J = tan(45);
printf("\n\lf", J);
```

# 圆周长

```
const float PI = 3.14159;
float radius;
float circumstance;
float area;

printf("\nPlease enter a radius:");
scanf("%f", &radius);

circumstance = 2 * PI * radius;
area = PI * radius * radius;

printf("\nCircumstance: %f", circumstance);
printf("\nArea is %f", area);
```

# 斜边

```c
#include <stdio.h>
#include <math.h>
int main(){
    double A;
    double B;
    double C;

    printf("Enter side A:");
    scanf("%lf", &A);
    printf("\nEnter side B:");
    scanf("%lf", &B);

    C = sqrt(A*A + B*B);
    // C = sqrt(pow(A, 2) + pow(B, 2));

    printf("Side C:%lf", C);
    return 0;
}
```

# if语句

```
int age;
printf("Enter your age: ");
scanf("%d", &age);
if(age >= 18){
    printf("enough old");
}
else if(age == 0){
	printf("just born");
}
else if(age < 0){
    printf("not born");
}
else{
    printf("Young");
}
```

# switch

一个值多个情况的相等测试

```
switch(grade){
    case 'A':
        printf("perfect");
        break;
    case 'B':
        printf("2");
        break;
    case 'C':
        printf("3");
        break;
    default:
        printf("enter valid grade");
}
```

# 温度转换

```
#include <ctype.h>
char unit;
float temp;

printf("\nEnter the temp in (F) or (C): ");
scanf("%c", &unit);
unit = toupper(unit);

if(unit == 'C'){
    // printf("The temp is currently in C");
    printf("\nEnter the temp: ");
    scanf("%f", &temp);
    temp = (temp * 9 / 5) + 32;
    printf("\nThe temp is: %.1f", temp);
}
else if(unit == 'F'){
    // printf("The temp is currently in F");
    printf("\nEnter the temp: ");
    scanf("%f", &temp);
    temp = ((temp - 32) * 5) / 9;
    printf("\nThe temp is: %.1f", temp);
}
else{
    printf("\n %c is not a valid unit", unit);
}
```

# 计算器

声明运算方式，数字1，数字2，结果

```
char operator;
float num1;
float num2;
float result;

printf("Enter a +-*/: ");
scanf("%c", &operator);
printf("Enter num1: ");
scanf("%f", &num1);
printf("Enter num2: ");
scanf("%f", &num2);

switch(operator){
    case '+':
        result = num1 + num2;
        printf("\n%.2f", result);
        break;
    case '-':
        result = num1 - num2;
        printf("\n%.2f", result);
        break;
    case '*':
        result = num1 * num2;
        printf("\n%.2f", result);
        break;
    case '/':
        result = num1 / num2;
        printf("\n%.2f", result);
        break;
    default:
        printf("%c is not valid", operator);
}
```

# 逻辑运算符

&&

||

!

# function

```
void func()
{
    printf("\nsentence1");
    printf("\nsentence2");
    printf("\nsentence3");
    printf("\nsentence4");
}
int main(){
    func();
    func();
    //调用2次
    return 0;
}
```

## 错误

- 字符串不能用单引号
- void的参数要带前面的**数据类型**
- void的参数是形参，顺序要和调用的参数顺序相同
- void的参数可以改名

```
void func(char name[], int age)
{
    printf("\nsentence1 %s", name);
    printf("\nsentence2 %d", age);
    printf("\nsentence3");
    printf("\nsentence4");
}
int main(){
    char name[] = "ren";
    int age = 21;

    func(name, age);

    return 0;
}
```

# return

将一个值返回给调用函数

```
void square(float x)
{
    return x * x;
}
int main(){
    float x = square(3.14);
    printf("%f", x);
    return 0;
}
```

# 三元运算符

本例返回一个整数，所以用int，没用void???

```
int findMax(int x, int y)
{
    return (x > y) ? x : y;
}
int main(){
    int max = findMax(5, 4);
    printf("%d", max);
    return 0;
}
```

# 函数原型

主函数之前，声明的，没有函数体

确保函数调用使用正确的参数数量和类型。编辑器会报错

```c
void hello(char[], int);
int main(){
    char name[] = "ren";
    int age = 21;

    hello(name);
    return 0;
}
void hello(char name[],int age)
{
    printf("\nHello %s", name);
    printf("\nYou are %d years old", age);
}
```

# 字符串函数

```c
#include <string.h>
char string1[] = "Bro";
char string2[] = "Code";

strlwr(string1);//全小写
strupr(string1);//全大写
strcat(string1, string2);//第二个字符串加在第一个字符串后面
strncat(string1, string2, 1);//第二个的前x个字符放在第一个字符串后
strcpy(string1, string2);//后一个字符串替代前一个字符串
strncpy(string1, string2, 2);//后一个字符串的前x位，替代前一个字符串的前x位
strset(string1, '?');//字符串全用给定的字符的代替
strnset(string1, 'x', 1);//字符串的前x位用给定字符代替
strrev(string1);//字符串倒转
int result = strlen(string1);//字符串长度作为整数返回
int result = strcmp(string1, string2);//比较2个字符串，相等返回0，不相等返回非0
int result = strncmp(string1, string2, 1);//比较两个字符串的指定字符是否相等
int result = strcmpi(string1, string1);//不区分大小写，比较2个字符串，相等返回0，不相等返回非0
int result = strnicmp(string1, string2, 1);//不区分大小写，比较两个字符串的指定字符是否相等
```

# for循环

```
for(int i = 1; i < 10; i++){
    printf("%d\n", i);
}
return 0;
```

# while循环

先判断，再循环，条件为真时，重复语句或语句组。

```
char name[25];

printf("\nWhat's your name?: ");
fgets(name, 25, stdin);
name[strlen(name) - 1] = '\0';

while(strlen(name) == 0)
{
    printf("\nYou did not enter your name");
    printf("\nWhat's your name?: ");
    fgets(name, 25, stdin);
    name[strlen(name) - 1] = '\0';
}
printf("Helllo %s", name);
```

# do-while

先执行，后判断

```
int number = 0;
int sum = 0;

do{
    printf("Enter a # above 0: ");
    scanf("%d", &number);
    if(number > 0)
    {
        sum += number;
    }
}while(number > 0);
```

# 嵌套循环

scanf("%c");缓冲区

```
int row;
int column;
char symbol;
printf("Enter a row: ");
scanf("%d", &row);
printf("Enter a column: ");
scanf("%d", &column);
scanf("%c");
printf("Enter a symobl: ");
scanf("%c", &symbol);

for(int i = 1; i <= row; i++)
{
    for(int j = 1; j <= column; j++)
    {
        printf("%c", symbol);
    }
    printf("\n");
}
```

# continue,break

continue跳过，后面的正常循环

break循环到它前一个，后面停止循环

```
for(int i = 1; i <= 20; i++)
{
    if(i == 13)
    {
        continue;
    }
    printf("%d\n", i);
}
```

# 数组

存储相同数据类型

```
float prices[] = {5.0, 10.0, 15.0};
整数数组int array[] = {3, 7, 4};
printf("$%.2f", prices[0]);
```

分配

```
prices[2] = 2.0;
```

声明时[]里面的数字可以多于给定的值，后续再分配

# 循环遍历打印数组

```
float prices[] = {5.0, 10.0, 15.0};
// printf("%d bytes\n", sizeof(prices));
for(int i =0; i < sizeof(prices)/sizeof(prices[0]); i++)
{
    printf("$%.2f\n", prices[i]);
}
```

# 二维数组

必须指定每个数组中元素的最大数量

## 声明数组

直接赋值

- [行数][列数]

```
int numbers[2][3] = {
                     {1, 2, 3},
                     {4, 5, 6}
                    };
```

- 先声明，后分配

```
int numbers[2][3];
numbers[0][1] = ;5
```

## 遍历数组

```c
//声明赋值后
int rows = sizeof(numbers)/sizeof(numbers[0]);//数组总大小÷每行大小
int columns = sizeof(numbers[0])/sizeof(numbers[0][0]);//第一行的大小÷第一个元素的大小

printf("rows: %d\n", rows);
printf("columns: %d\n", columns);

for(int i = 0; i < rows; i++)
{
    for(int j = 0; j < columns; j++)
    {
        printf("%d", numbers[i][j]);
    }
    printf("\n");
}
```

# 字符串数组

第二组[]内，指定每个元素的最大大小

不能直接更改其中一个值

## 应用strcpy

```c
#include <string.h>
char cars[][10] = {"abcd1", "efgh2", "hijk3"};

strcpy(cars[0], "uxyz4");//更改元素

for(int i = 0; i < sizeof(cars)/sizeof(cars[0]); i++)
{
    printf("%s\n", cars[i]);
}
```

# 交换两个变量的值

声明第三个变量临时存储某个值

## 单个字符

```
char x = 'X';
char y = 'Y';
char temp;

temp = x;
x = y;
y = temp;

printf("x = %c\n", x);
printf("y = %c\n", y);
```

## 字符串

声明字符串x,y大小相同（如15），否则第二个字符串长度小于第一个长度时，第一个会是空值

```
char x[15] = "water";
char y[15] = "lemonade";
char temp[15];

strcpy(temp, x);
strcpy(x, y);
strcpy(y, temp);


printf("x = %s\n", x);
printf("y = %s\n", y);
```

# 对数组排序

## 冒泡，整数数组排序

冒泡法：每次比较数组中的相邻两个数组元素的值，将较小的数排在较大的数前面。

遍历次数：计算数组大小

从第一个索引开始，检查左边的元素是否大于右边的元素

```
void sort(int array[], int size)
{
    for(int i = 0; i < size - 1; i++)
    {
        for(int j = 0; j < size - i - 1; j++)
        {
            if(array[j] > array[j+1])
            {
                int temp = array[j];
                array[j] = array[j+1];
                array[j+1] = temp;
            }
        }
    }
}
void printArray(int array[], int size)
{
    for(int i = 0; i < size; i++)
    {
        printf("%d ", array[i]);
    }
}
int main(){
    int array[] = {7, 1, 4, 2, 3};
    int size = sizeof(array)/sizeof(array[0]);
    sort(array, size);
    printArray(array, size);
    return 0;
}
```

## 字符数组排序

其他的不变

```
void sort(char array[], int size)
void printArray(char array[], int size)
printf("%c ", array[i]);
char array[] = {'A', 'F', 'D'};
```

# 结构体

int之外声明struct，函数体中声明变量，类似class

```
struct Player
{
    char name[12];
    int score;
};
int main(){
    struct Player player1;
    struct Player player2;

    strcpy(player1.name, "Bro");
    player1.score = 4;
    strcpy(player2.name, "Ren");
    player2.score = 2;

    printf("%s\n", player1.name);
    printf("%d\n", player1.score);
    printf("%s\n", player2.name);
    printf("%d\n", player2.score);

    return 0;
}
```

# 类型定义typedef

保留关键字，给现有的数据类型起一个别名

```
typedef struct
{
    char name[25];
    char password[12];
    int id;
}User;

int main(){
    User user1 = {"Bro", "password1", 123456};
    User user2 = {"Bruch", "password2", 123789};

    printf("%s\n", user1.name);
    printf("%s\n", user1.password);

    return 0;
}
```

# 结构体数组

```
struct Student
{
    char name[12];
    float gpa;
}User;

int main(){
    struct Student student1 = {"Spngebob", 3.0};
    struct Student student2 = {"Patrick", 5.0};
    struct Student student3 = {"Sangdy", 3.5};
    struct Student student4 = {"Squid", 4.0};

    struct Student students[] = {student1, student2, student3, student4};
    for(int i = 0; i < sizeof(students)/sizeof(students[0]); i++)
    {
        printf("%-12s\t", students[i].name);
        printf("%.2f\n", students[i].gpa);
    }
    return 0;
}
```

# 枚举

枚举不是字符串，可以视为整数

```
enum　枚举名　{枚举元素1,枚举元素2,……};
```

```
//先定义枚举类型，再定义枚举变量
enum Day{Sun = 1, Mon, Tue, Wed, Thu, Fri, Sat};

int main(){
    enum Day today = Sat;
    // printf("%d", today);
    if(today == Sun || today == Sat)
    {
        printf("\nIt's the weekend!");
    }
    else
    {
        printf("\nI have to work today ");
    }
    return 0;
}
```

# 随机数

是伪随机数，一组统计上随机的值或元素

```
#include <stdlib.h>
#include <time.h>
```

```
int main(){
    //当前时间作为参数
    srand(time(0));
    //数字存储在一个变量中
    //0-32767的随机数
    //用取模运算符，和想要的最大数
    int number1 = (rand() % 6) + 1;
    printf("%d", number1);
    return 0;
}
```

# 数字猜测游戏

?????guesses出错

```
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

//先定义枚举类型，再定义枚举变量

int main(){
    const int MIN = 1;
    const int MAX = 100;
    int guess;
    int guesses;
    int answer;

    srand(time(0));
    answer = (rand() % MAX) + MIN;

    do{
        printf("Enter a guess: ");
        scanf("%d", &guess);
        if(guess > answer)
        {
            printf("Too high\n");
        }
        else if(guess < answer)
        {
            printf("Too low\n");
        }
        else{
            printf("Correct\n");
        }
        guesses++;
    }while(guess != answer);

    printf("***********\n");
    printf("answer: %d\n", answer);
    printf("guesses: %d\n", guesses);
    printf("***********");

    return 0;
}
```

# 测验游戏？？？？

```
#include <stdio.h>
#include <ctype.h>


//先定义枚举类型，再定义枚举变量

int main(){
    //创建二维字符数组存储问题
    char questions[][100] = {"1.question1?"
                             "2.question2?"
                             "3.question3?"};
    char options[][100] = {"A. 123", "B. 456", "C. 789", "D. 134",
                           "A. avc", "B. awg", "C. dgg", "D. dfd",
                           "A. 4t4", "B. 2v2", "C. 3vv", "D. 65v"};
    char answers[3] = {'B', 'A', 'B'};
    int numbersOfQuestions = sizeof(questions)/sizeof(questions[0]);

    char guess;
    int score;

    printf("Quiz Game\n");
    for(int i = 0; i < numbersOfQuestions; i++)
    {
        printf("*******************\n");
        printf("%s\n", questions[i]);//循环遍历问题
        printf("*******************\n");
        //显示可能的选项
        for(int j = (i * 4); j < (i * 4) + 4; j++)
        {
            printf("%s\n", options[j]);
        }
        printf("guess: ");
        scanf("%C", &guess);
        scanf("%C");

        guess = toupper(guess);

        if(guess == answers[i]);
        {
            printf("CORRECT\n");
        }
        else
        {
            printf("WORRING\n");
        }
        printf("FINAL SCORE: %d/%d\n", score, numbersOfQuestions);
    }
    return 0;
}
```

# 位运算符





# 内存地址

- 内存是RAM中字节数组（街道）
- 内存块是内存中的一个字节单元，用于存储一些值（街道上的房子）
- 内存地址是内存块在RAM中的位置地址（房子的地址）
- 内存地址称为变量名

声明一个变量时分配一些内存块存储一些值

每个字符的大小都是一个字节

```
char a = 'X'; 
char b = 'Y'; 
char c = 'Z'; 

printf("%d bytes\n", sizeof(a));
printf("%d bytes\n", sizeof(b));
printf("%d bytes\n", sizeof(c));

//显示地址%p
//十六进制的地址
printf("%p\n", &a);
printf("%p\n", &b);
printf("%p\n", &c);
```

1. 标准十进制值0-9
2. 十六进制0-9，a-f

- char 1bytes内存
- short是两个字节的内存
- int 4bytes内存
- double 8bytes内存
- char b[2]; 需要2个元素，1*2=2bytes内存
- short b[3]; 需要3个元素，2*3=6bytes内存
- int b[5];  需要5个元素，4*5=20bytes内存

# 指针

变量的引用，将一个内存地址作为值指向另一个变量、数组

创建一个指针，确保他们与要指向的变量有相同的数据类型

使用*(间接操作符)

内部存储的值是一个地址，通过间接操作符访问地址上的值

```c
int main(){
    int age = 21;
    int *pAge = &age;

    printf("address of age: %p\n", &age);//变量的地址
    printf("address of age: %p\n", pAge);

    printf("size of age: %d bytes\n", sizeof(age));
    printf("size of pAge: %d bytes\n", sizeof(pAge));
    

    printf("value of age: %d\n", age);//变量的值
    printf("value at stored address: %d\n", *pAge);//值在地址操作符


    return 0;
}
```

指针作为参数传递给函数

```c
void printAge(int age)
{
    printf("You are %d years old\n", age);
}
int main(){
    int age = 21;
    int *pAge = &age;
    printAge(age);
    return 0;
}

void printAge(int *pAge)
{
    printf("You are %d years old\n", *pAge);
}
int main(){
    int age = 21;
    int *pAge = &age;
    printAge(pAge);
    return 0;
}
```

声明指针最好赋一个null值

```
int pAge = NULL;
pAge = &age;
```

# 文件写入

- 数据类型file
- *pF指向文件的指针
- 第二个参数：模式，w写入，a追加，r读取

将一行文本写入文件，传入指针pF

```
FILE *pF = fopen("test.txt", "w");
fprintf(pF, "LiRen");
fclose(pF);
```

追加文件

```
FILE *pF = fopen("test.txt", "a");
```

删除文件，上面那些注释

```
if(remove("test.txt") == 0)
{
    printf("That file was deleted successfully ");
}
else
{
    printf("That file was not deleted");
}
```

指定路径建立文件，两个\\

```
FILE *pF = fopen("C:\\Users\\Admin\\Desktop\\test.txt", "w");
```

# 文件读取

## 读取单行

缓冲区，充当一个容器，一个字符数组保存文档中的一行

```
FILE *pF = fopen("C:\\Users\\Admin\\Desktop\\test.txt", "r");
char buffer[255];

fgets(buffer, 255, pF);//读取文件单行
printf("%s", buffer);

fclose(pF);
```

## 读取全部内容，while循环

注意：NULL大写

```
while (fgets(buffer, 255, pF) != NULL)
{
    printf("%s", buffer);  
}
```

## 确定文件是否存在，if-else

```
if(pF == NULL)
{
    printf("Unable to open file");
}
else
{
    while (fgets(buffer, 255, pF) != NULL)
    {
        printf("%s", buffer);  
    }
}
```

# 井字游戏


