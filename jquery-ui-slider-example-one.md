#jQuery UI Slider 示例（一）

jQuery Slider 组件可以把选中的 HTML 元素变成滑动条 UI 控件，滑动条可以支持多个滑块用来设置单个值或一个值域。

##基本用法

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <title>jQuery UI Demos</title>
    <link rel="stylesheet" href="themes/trontastic/jquery-ui.css" />
    <script src="scripts/jquery-1.9.1.js"></script>
    <script src="scripts/jquery-ui-1.10.1.custom.js"></script>
    <script>
        $(function () {
            $("#slider").slider();
        });
    </script>
</head>
<body>
    <div id="slider"></div>

</body>
</html>
```

![](images/50.png)

##多个滑块选择值域

Slider 支持使用两个滑块来选择一个值域，通过 min,max 指定大范围， values 指定当前选择的值域。

```
range: true
min: 0,
max: 500,
values: [ 75, 300 ],
```

完整代码如下：

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <title>jQuery UI Demos</title>
    <link rel="stylesheet" href="themes/trontastic/jquery-ui.css" />
    <script src="scripts/jquery-1.9.1.js"></script>
    <script src="scripts/jquery-ui-1.10.1.custom.js"></script>
    <script>
        $(function () {
            $("#slider-range").slider({
                range: true,
                min: 0,
                max: 500,
                values: [75, 300],
                slide: function (event, ui) {
                    $("#amount").val("$" + ui.values[0]
                        + " - $" + ui.values[1]);
                }
            });
            $("#amount").val("$"
                + $("#slider-range").slider("values", 0) +
              " - $" + $("#slider-range").slider("values", 1));
        });
    </script>
</head>
<body>

    <p>
        <label for="amount">Price range:</label>
        <input type="text" id="amount" 
               style="border: 0; color: #f6931f; 
               font-weight: bold;" />
    </p>

    <div id="slider-range"></div>


</body>
</html>
```

![](images/51.png)

