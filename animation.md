#动画效果

前面的 hide/show,slide in/out 其实也具有动画效果，本篇介绍使用 animate()实现自定义动画效果。

##基本语法如下：

$(selector).animate({params},speed,callback);

必选的参数为 params,定义 CSS 用于动画效果的的属性。

可选参数 speed 给出了淡入效果的时间，可以使用 “slow”,”fast” 或是数值（微秒）
第二个可选参数为回调函数，在 animate()方法结束后调用。

比如下面的例子，将一个 <div> 标记移动到其 Left 属性等于250px.

```
$("button").click(function(){
  $("div").animate({left:'250px'});
});
```

要注意的是，缺省情况下，所有 HTML 元素的位置的固定的，不能移动，因此如果需要修改 HTML 元素的位置，需要事先将它们的 CSS 属性的位置设置为 relative, fixed, 或 absolute。

##使用 animate 修改多个属性

下面的例子，可以使用 animate 同时修改多个属性：

```
$("button").click(function(){
  $("div").animate({
    left:'250px',
    opacity:'0.5',
    height:'150px',
    width:'150px'
  });
});
```

注意：基本所有的 CSS 属性都可以在 animation 中使用，颜色修改不在 jQuery 核心库中，需要Color Animiation 插件来完成。

##使用属性相对值

对于 CSS 属性，除了上面使用的绝对大小，也可以使用相对值来定义，使用 “+”“-”。

```
$("button").click(function(){
  $("div").animate({
    left:'250px',
    height:'+=150px',
    width:'+=150px'
  });
});
```

##使用预定义的值

也可以使用预定义的值为属性赋值。比如”show”, “hide”, 或 “toggle”:

```
$("button").click(function(){
  $("div").animate({
    height:'toggle'
  });
});
```

##使用队列功能

缺省 jQuery 支持将多个 animation 功能串起来构从一个队列，然后一个一个的执行队列中的指令。

比如：

```
$("button").click(function(){
  var div=$("div");
  div.animate({height:'300px',opacity:'0.4'},"slow");
  div.animate({width:'300px',opacity:'0.8'},"slow");
  div.animate({height:'100px',opacity:'0.4'},"slow");
  div.animate({width:'100px',opacity:'0.8'},"slow");
});
```

或

```
$("button").click(function(){
  var div=$("div");
  div.animate({left:'100px'},"slow");
  div.animate({fontSize:'3em'},"slow");
});
```