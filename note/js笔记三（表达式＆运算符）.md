# 表达式＆运算符
* 表达式是语言的基本构成，具有一定的意义；多个表达式可以通过运算符进行连接，变成更复杂的表达式
+ 浏览器会计算表达式，并得出一个结果，我们把这个结果成为表达式的返回值
* console.log(1+4);浏览器会输出4
> 运算符
* 运算符：算数运算符：+，-，*，/，%（求余）
+ %（求余）：余数是1为奇数，余数为0为偶数
* 自增/自减：让数据（数值）自动加一/减一
> 比较运算符
+ 比较运算符：<=,<,>=,>,= =,===
* 用来比较两个值（表达式）的关系比较的结果是布尔 true/false
+ ==：相等，只会判断两个表达式的值；
* ===：全等即判断值，又要判断数据类型
+ ！=：非相等
* ！==：非全等
> 逻辑运算符
* 用来表示两个判断之间的关系
+ &&（逻辑与）：当有一方判断为假的时候，结果都为假，当两方判断为真的时候，结果才是真
```js
var one = 1;
var two = 2;
console.log(one>0&&two<0);
console.log(one<0&&one>0);
console.log(one>0&&two>0);
```
* 逻辑或||：当有一方判断为真的时候结果都是真，当两方判断都为真的时候都为真，都为假的时候都为假
+ 逻辑非！：非真即假，非假即真
```js
var bool = true;
var bool1 = false;
console,log(!bool,!false);
```
> 赋值运算符
* 赋值运算符：既可以运算，又可以赋值，把结果赋值给其中一个变量
+ one+=tree;等价于one=one+tree;先运算，再把结果给等号左边的变量
## 条件执行
* 条件执行：当程序满足条件之后再执行相应的操作，使用条件语句
> if语句
+ if语句：if(判断的表达式){
    判断为真时执行此操作
}else{
    判断为假时执行此操作
}
```js
var num = 5;
if(num>4){
    console.log("num大于4")
}else{
    console.log("num小于4")
}
```
> switch语句
* switch语句：通过关键字switch创建语句，小括号中填写要判断的变量
+ 通过关键字case表示一种情况，在冒号后面写情况满足时执行操作，通过break关键字来终止此次判断
* 通过关键字befault来表示当变量不满足所有情况时，执行befault冒号后面的操作
```js
var one = 88;
var two = 99;
var sing = "+";
switch(sing){
    case"+":console.log(one+two);break;
    defaule:console.log("附号错误");break;
}
```
> switch实例题
* switch实现一个四则运算
```js
function count(m,s,n){
    switch(S){
        case"+":result = m+n;break;
        case"*":result = m*n;break;
    }
    retum result;
}
var result = coun(5,"+",6);
console.log(result);
var result = count(5,"*",6);
console.log(result);
```
+ retum:返回值
> 条件运算符
* 条件运算符：用来进行简单判断和执行简单操作
+ 语法：判断的表达式（？）判断为真时的操作，为假时的操作
```js
var one = 1;
one>3?console.log(true);console.log(false);
```
> for循环语句
* 循环执行
```js
for (var i = 1;i<10;i++){
    console.log(i)
}
```
* 循环执行：是使用循环语句，重复多次的执行代码
+ 语法：for(初始值;判断;计数器){
    当判断为真时执行此操作
}
* 注意：for语句必须带有计数器，否则会陷入死循环
+ document.write()将内容输出在页面上
> while语句
* while语句：经常用来循环已知变量和条件的关系
+ 语法：while(判断的表达方式){
    判断为真时执行的代码；
    计数器；
}
```js
var n = 0;
while(n<9){
    console.log(n);
    n++;
}
```
