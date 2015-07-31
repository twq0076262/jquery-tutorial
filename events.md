#Events

学习了 jQuery 的选择器，就可以针对选择的 HMTL 标记或是元素添加事件处理，事件包括按键，鼠标，单击按钮等。

下面为常见的 DOM 事件：


##jQuery事件处理的语法

在 jQuery 中，大部分的 DOM 事件都有对应的 jQuery 事件，比如为所有 <p> 标记添加单击事件处理：

```
$("p").click();
```

下一步添加单击事件的处理函数，你必须传一个回调函数给单击事件：

```
$("p").click(function(){
  // action goes here!!
});
```

##常见的jQuery事件

###$(document).ready()

文档准备好事件，在文档完全载入后执行。

###click()

用户单击某个 HTML 元素后调用，比如下面的例子中用户点击 <p> 标记部分后隐藏该标记的内容：

```
$("p").click(function(){
  $(this).hide();
});
```
###dblclick()

双击某个 HTML 标记时调用，比如下面代码在双击 <p> 元素时隐藏其内容：

```
$("p").dblclick(function(){
  $(this).hide();
});
```
###mouseenter()

在鼠标进入某个 HTML 元素时触发，例如：

```
$("#p1").mouseenter(function(){
  alert("You entered p1!");
});
```
###mouseleave()

在鼠标进入离开某个 HTML 元素时触发，例如：

```
$("#p1").mouseleave(function(){
  alert("Bye! You now leave p1!");
});
```
###mousedown()
在按下鼠标左键时触发，例如：

```
$("#p1").mousedown(function(){
  alert("Mouse down over p1!");
});
```

###mouseup()
在某个元素上释放鼠标左键时触发，例如：

```
$("#p1").mouseup(function(){
  alert("Mouse up over p1!");
});
```

###hover()
在鼠标指针放在某个元素之上时触发，为 mouseenter 和 mouseleave 的组合，它的第一个回调函数中鼠标进入时调用，第二个回调函数在鼠标离开时执行，例如：

```
$("#p1").hover(function(){
  alert("You entered p1!");
  },
  function(){
  alert("Bye! You now leave p1!");
});
```
###focus()
当某个表单输入域获得焦点时调用,例如：

```
$("input").focus(function(){
  $(this).css("background-color","#cccccc");
});
```

###blur()
当某个表单输入域失去焦点时调用,例如：

```
$("input").blur(function(){
  $(this).css("background-color","#ffffff");
});
```










