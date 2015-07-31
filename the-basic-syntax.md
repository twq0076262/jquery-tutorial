#基本语法

学习 jQuery 之前需要你有下面几个方面的基本知识

- HTML
- CSS
- JavaScript

##jQuery 的基本语法

$(*selector*).*action*()

- $ 符合定义这是一个 jQuery 语句
- (*selector*) 用来选择某个 HTML 元素，其语法和 CSS 的 selector语法一样。
- *action*() 定义操作该 HTML 元素的方法。

比如：

$(this).hide() – 隐藏当前元素.

$(“p”).hide() – 隐藏所以元素.

$(“.test”).hide() -隐藏所以类名为test的元素.

$(“#test”).hide() – 隐藏ID为test的元素。

##文档准备好事件

几乎所有的 jQuery 都有如下的代码：

```
$(document).ready(function(){

   // jQuery methods go here...

 }); 
 
```

这为 Document Ready 事件处理器以防止 jQuery 在页面没有完成载入前就执行。从而可以避免下面类似情况发生：

试图隐藏尚未创建好的元素

试图获取尚未载入的图片的大小

这个方法也可以使用下面简化的方法：

```
$(function(){

   // jQuery methods go here...

 }); 
 
```

你可以选择你喜欢的方式，但通常还是采用 $(document).ready(function(){ 的方式以便于代码的阅读。