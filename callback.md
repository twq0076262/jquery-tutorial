#回调函数

JavaScript 语句是一行一行执行的，然而对于前面的动画效果语句，后面的语句可以在动画效果完成前就执行，因此可能会造成错误的结果。
所以之前的 hide,show,fadeIn,fadeOut,slideIn,slideOut,animation 都支持一个 callback 可选参数，支持为这些方法添加一个回调函数，在动画完成之后调用。

典型的语法如下：

$(selector).hide(speed,callback);

比如，下面的例子中<p>隐藏之后执行：

```
$("button").click(function(){
  $("p").hide("slow",function(){
    alert("The paragraph is now hidden");
  });
});
```

而下面的例子的 Alert 在

隐藏完成之前就显示。

```
$("button").click(function(){
  $("p").hide(1000);
  alert("The paragraph is now hidden");
});
```
