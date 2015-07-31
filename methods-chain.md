#方法链

jQuery 支持将多个方法链接在一起，比如介绍的多个 animation()，这个链接也可以应用到其它方法，构成一个方法链。

使用这个方法，对于同一个元素，链接多个方法，浏览器无需多次查找 HTML 元素。

下面的方法，可以把 css,slideUp,slideDown 串接在一起：

```
$("#p1")
	.css("color","red")
	.slideUp(2000)
	.slideDown(2000);
```