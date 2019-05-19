## 从 jQuery 到 Vue

### 什么是 jQuery

jQuery是一个快速，小巧，功能丰富的JavaScript库。对浏览器原生的API进行封装，使得HTML文档遍历和操作，事件处理，动画和Ajax变得很简单，同时兼容多种浏览器。

简单、兼容

```javascript
//https://codesandbox.io/embed/eloquent-yonath-buufs
$('.app button').text('Submit')	
```

```javascript
var url = "test.json";
// jQuery Ajax
$.ajax({
  dataType: "json",
  url: url,
  data: data,
  success: success
});

// 原生
var xmlhttp = new XMLHttpRequest();
xmlhttp.onreadystatechange = function() {
    if (this.readyState == 4 && this.status == 200) {
        var json = JSON.parse(this.responseText);
        success(json);
    }
};
xmlhttp.open("GET", url, true);
xmlhttp.send();
```

### 为什么不需要jQuery
 [You-Dont-Need-jQuery](https://github.com/nefe/You-Dont-Need-jQuery)
 - 浏览器已经有了很完善的API，相当于把jQuery内置了
 - 对于React, Angular和Vue等框架来说直接操作dom是反模式
 - DOM操作耗时耗性能（the selector function is over an *order of magnitude slower*than the native implementation. While this isn’t a problem for small applications the inefficiency grows with continued）
 - React abstracts direct DOM manipulation from the developer and instead tucks it inside its virtual DOM diffing algorithm. The virtual DOM actually stores a lot of the element locations in memory - this makes it *more efficient than the native implementation*. Taking it a step further, the diffing algorithm works to ensure the minimum number of methods are invoked during the update.

### 什么是Vue



虚拟DOM

声明式
响应式