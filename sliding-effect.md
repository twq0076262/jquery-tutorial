#滑动效果

jQuery 支持使用下面方法来实现 HTML 元素的滑动效果：

- slideDown()
- slideUp()
- slideToggle()

slideDown 方法

用来实现向下滑动动画效果，其基本语法为：

```
$(selector).slideDown(speed,callback);
```

可选参数 speed 给出了淡入效果的时间，可以使用 “slow”,”fast” 或是数值（微秒）
第二个可选参数为回调函数，在 slideDown()方法结束后调用。

下面例子点击按钮 #panel 将采用下滑方式显示出来：

```
<!DOCTYPE html>
<html>
<meta charset="utf-8">
<title>JQuery Demo</title>
<script src="scripts/jquery-1.9.1.js"></script>
<script>
    $(document).ready(function () {
        $("#flip").click(function () {
            $("#panel").slideDown("slow");
        });
    });
</script>

<style type="text/css">
    #panel, #flip
    {
        padding: 5px;
        text-align: center;
        background-color: #e5eecc;
        border: solid 1px #c3c3c3;
    }

    #panel
    {
        padding: 50px;
        display: none;
    }
</style>
</head>
<body>

    <div id="flip">Click to slide down panel</div>
    <div id="panel">Hello world!</div>

</body>
</html>
```

slideUp 方法

用来实现向上滑动动画效果，其基本语法为：

$(selector).slideUp(speed,callback);

可选参数 speed 给出了淡入效果的时间，可以使用 “slow”,”fast” 或是数值（微秒）
第二个可选参数为回调函数，在 slideUp()方法结束后调用。

```
$("#flip").click(function(){
  $("#panel").slideUp();
});
```

slideToggle 方法

用来实现交替显示向上向下滑动动画效果，如果之前是下滑显示，slideToggle 则显示 slideUp(),反之显示 slideDown

其基本语法为：

$(selector).slideToggle(speed,callback);

可选参数 speed 给出了淡入效果的时间，可以使用 “slow”,”fast” 或是数值（微秒）
第二个可选参数为回调函数，在 slideUp()方法结束后调用。

```
$("#flip").click(function(){
  $("#panel").slideToggle();
});
```

