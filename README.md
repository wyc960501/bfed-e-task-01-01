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







### 2、请说出下列最终的执行结果，并解释为什么？
```
var tmp = 123;
if(true){
  console.log(tmp);
  let tmp;
}
```



### 3、结合ES6新语法，用最简单的方式找出数组中的最小值？
```
var arr = [12,34,32,89,4];
```

### 4、请详细说明var,let,const三种声明变量的方式之间的具体差别？



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

### 6、简述Symbol类型的用途？

### 7、说说什么是浅拷贝，什么是深拷贝？

### 8、谈谈你是如何理解JS异步编程的，Event Loop是做什么的，什么宏任务，什么是微任务？

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


### 10、请简述TypeScript与JavaScript之间的关系？

### 11、请谈谈你所认为的TypeScript优缺点？
