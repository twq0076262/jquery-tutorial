#终止动画

jQuery 的使用 stop()方法在动画结束之前停止动画。

基本语法如下：

$(selector).stop(stopAll,goToEnd);

可选参数 stopAll 指明是否同时清除“动画队列”，缺省为 false.意味着只停止当前活动的动画，之后的动画则继续运行。

可选参数 goToEnd 指明是否立即结束当前动画，缺省为 false.

因此缺省的 stop()动作为终止指定 HTML 元素的当前动画效果。如：

```
$("#stop").click(function(){
  $("#panel").stop();
});
```