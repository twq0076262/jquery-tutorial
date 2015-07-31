#Selectors

jQuery Selector 是 jQuery库中非常重要的一个组成部分。

jQuery Selector 用来选择某个 HTML 元素，其基本语句和 CSS 的选择器（Selector）是一样的，所有 jQuery selector 都是以 $() 开始。

##选择 HTML 标记

选择某个HTML元素的方法是直接使用该元素的标记名称，比如选择所有 <p> 元素

```
$("p")
```

下面的例子当用户点击一个按钮时，隐藏所有的

元素

```
$(document).ready(function(){
   $("button").click(function(){
     $("p").hide();
   });
 });
```

##id 选择

jQuery #id 选择器用来选择定义了 id 属性的元素，网页上元素的 id 应保证是唯一的，你可以使用 id 来选择单个唯一的元素。

比如下面的例子，当点击按钮时，只会隐藏 id 为 test 的元素。

```
<!DOCTYPE html>
html>
head>
script src="//ajax.googleapis.com/ajax/libs/jquery/1.8.3/jquery.min.js">
/script>
script>
$(document).ready(function(){
  $("button").click(function(){
    $("#test").hide();
  });
});
/script>/head>

body>
h2>This is a heading</h2>
p>This is a paragraph.</p>
p id="test">This is another paragraph.</p>
button>Click me</button>
/body>

/html>
```

##.class 选择器

jQuery .class 选择器选择所有定义了 class 属性为制定值的所有元素，比如下面的例子 隐藏所有类名称为 test 的元素：

```
<!DOCTYPE html>
html>
head>
script src="//ajax.googleapis.com/ajax/libs/jquery/1.8.3/jquery.min.js">
/script>
script>
$(document).ready(function(){
  $("button").click(function(){
    $(".test").hide();
  });
});
/script>
/head>
body>

h2 class="test">This is a heading</h2>
p class="test">This is a paragraph.</p>
p>This is another paragraph.</p>
button>Click me</button>
/body>
/html>
```


