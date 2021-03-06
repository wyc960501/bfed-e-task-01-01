# 魏业昌 |Part1 | 模块一
### 1、请说出下列最终的执行结果，并解释为什么？
```
var a = [];
for (var i = 0; i < 10; i++){
  a[i] = function () {
    console.log(i);
  };
}
a[6]();
```
最终打印的结果是10，因为i作为一个由var声明的全局变量，在for循环中每循环一次i的值都会加1，当循环结束时i的值变为10。又因为赋值给数组a的函数里面的console.log(i)的i始终指向的是全局变量i,所以调用a[6]函数时，执行结果为10。

### 2、请说出下列最终的执行结果，并解释为什么？
```
var tmp = 123;
if(true){
  console.log(tmp);
  let tmp;
}
```
最终的结果报ReferenceError,虽然在全局作用域声明了变量tmp并赋值了123，但是因为在if块级作用域中又通过let声明绑定了变量tmp，所以此时块级作用域内的tmp指向的是由let声明的变量tmp,由于let声明的变量不存在变量提升，所以在声明前使用便会报错！


### 3、结合ES6新语法，用最简单的方式找出数组中的最小值？
```
var arr = [12,34,32,89,4];
console.log(Math.min(...arr));
```

### 4、请详细说明var,let,const三种声明变量的方式之间的具体差别？
var声明的变量，其作用域为该语句所在的函数内，声明的变量可以在声明前使用，但是值为undefined(存在变量提升),在相同的作用域内可以重复声明同一个变量；  
let声明的变量，其作用域为该语句所在的代码块内，声明的变量一定要在声明后使用，否则会报错（不存在变量提升），在相同的作用域内不能重复声明同一个变量；  
const声明的是常量，一旦声明常量的值就不能改变，声明的同时必须初始化，不存在变量提升，在相同作用域内不能重复声明同一个常量。

### 5、请说出下列代码最终输出的结果，并解释为什么？
```
var a = 10;
var obj = {
  a: 20,
  fn () {
    setTimeout(() => {
      console.log(this.a)
    });
  }
}
obj.fn();
```
最终打印的结果为20，因为this指向的是当前的obj对象，所以this.a指向的就是当前obj的属性a。

### 6、简述Symbol类型的用途？ 
作为对象的属性名使用，由于每一个Symbol值都是不相等的，所以把Symbol值作为标识符用于对象的属性名，可以保证不会出现同名的属性；  
使用Symbol定义类的私有属性/方法。

### 7、说说什么是浅拷贝，什么是深拷贝？
浅拷贝：对内存地址得复制，让目标对象指针和源对象指向同一片内存空间；  
深拷贝：拷贝对象的具体内容，内存地址不一样，自主分配，两个对象互不影响。

### 8、谈谈你是如何理解JS异步编程的，Event Loop是做什么的，什么宏任务，什么是微任务？
Js异步编程，不同于同步编程的请求-响应模式，其是一种事件驱动编程，请求调用函数或方法后，无需立即等待响应，可以继续执行其他任务，而之前任务响应后可以通过状态、通知和回调来通知调用者。  
Event Loop是一个程序结构，用于等待和发送消息和事件。    
宏任务：当前调用栈中执行的代码称为宏任务（如：setTimeout、setInterval);
微任务：当前宏任务执行完，在下一个宏任务开始之前需要执行的任务（如promise.then catch finally）.

### 9、将下面异步代码使用Promise改进？
```
setTimeout(function () {
  var a = "hello";
  setTimeout(function (){
    var b = "lagou";
    setTimeout(function(){
      var c = "I love you";
      console.log(a+b+c);
    },10);
  },10);
},10);
```
改进：
```
new Promise((resolve,reject) => {
    var a = "hello ";
    resolve(a);
}).then(function(res){
    var b = "lagou ";
    return res+b;
}).then(function(res){
    var c = "I love you";
    console.log(res+c);
});
```

### 10、请简述TypeScript与JavaScript之间的关系？
TypeScript是一门独立的编程语言，是JavaScript的超集，包含JavaScript、ES6、类型系统，以面向对象编程的方式使用JavaScript,代码最后编译成JavaScript。

### 11、请谈谈你所认为的TypeScript优缺点？
优点：提供强大的类型系统，可以在编译阶段发现错误；  
缺点：有一定的学习成本，对于小型项目开发会增加开发成本。

