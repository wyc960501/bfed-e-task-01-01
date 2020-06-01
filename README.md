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
