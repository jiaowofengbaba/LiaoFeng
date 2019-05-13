# js的数据类型
- - -
* ### 数据类型分为：数组，字符串，布尔，unll，nudefined，对象
- - -
> 字符串
```js
<script>
    var num = 1;
    var str = "hello world";
</script>
```
* 字符串数据是由字母，多个字母，字母+数字等形式组成，典型特征是有引导
> 布尔
```js
var bool = true;(真)
var bool = false;(假)
```
* 布尔书数据类型只有两个位 true (真) ，false (假)
+ 只有布尔类型也是字母，但是可不加引导，布尔类型经常用于判断
> 对象
* 对象是属性的无需集合，万物皆对象。
+ 花括号是对象的典型特征
* 语法：对象名 = {属性名：属性值，属性名：属性值}
```js
var object = {
    name:"youyou",
    age:12;
    sayname:function(){
        console.log(1)
    }
}
object.sayname();
console.log(object.name);
console.log(object.age);
```
* 当一个对象的属性值为函数的时候，我们就把这个对象的属性称为对象的方法
+ this：在对象里面通过关键字this来表示对象本身在对象里面获取对象属性
* this：属性名
> 数组
* 数组是元素的有序集合，典型特征是中括号，数组的值之间用逗号隔开，数组的序号被称为数组的下角标又叫索引值，通过数组名[索引值]可以获得索引值相对应的数组的项
```js
var arr = [1,2,3,4,5];
console.log(arr[0]);
console.log(arr[1]);
```
* 数组的长度：数组中包含值的个数
+ 语法：数组名.length;  
console.log(arr.length);
* 通过数组自带的push的方法，可以为数组的末尾添加元素
+ 语法：数组名.push(添加的值)；再把结果给一个变量
```js
var arr = [1,2,3,4,5];
arr.push(10);
console.log(arr);
```
* 语法：数组名,join("新的符号");  再把结果给一个变量
```js
var arr = [1,2,3,4,5];
var res = arr.join("+");
console.log(arr);
```
* 用法：arr = [1,2,3,4,5];  
       document.wite(arr.join("+"));
> 随堂习题
* 遍历数组、把数组中的偶数输出把数组中的基数加和并输出
```js
var arr = [11,22,33,44,55,66,77,88,99];
var res = 0;
for(var i = 0;i<arr.length;i++){
    if(arr[i]%2=0){
        console.log(arr[i]);
    }else{
        res+=i;
    }
}
console.log(res);
```
