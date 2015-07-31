#jQuery UI 基本工作过程

本篇介绍 JQuery UI 组件的基本工作过程，以进程条（Progressbar)为例介绍 JQuery UI 组件工作的基本过程。

##初始化

大部分 JQuery Ui 组件都可以保持其状态，因此为了能够跟踪 UI 组件的状态，jQuery UI 组件也有一个生命周期，这个生命周期从初始化开始，为了初始化一个 UI 组件，一般在某个 HTML 元素调用 UI 组件（插件）方法。，比如

```
$( "#elem" ).progressbar();
```

这个方法初始化 id=elem 的元素，因为我们调用 progressbar 没有带参数，因此将使用缺省属性来初始化进程条。我们可以通过传入配置的方法为 jQuery UI 组件修改缺省值。比如：

```
$( "#elem" ).progressbar({ value: 20 });
```

也可以一次传入多个参数来初始化 jQuery UI 组件，其它没有配置的属性还是使用其缺省值。这些属性也属于 jQuery UI 组件状态的一部分。初始化之后，如果需要修改这些属性，可以通过 option 方法来改变。

##方法

初始化 jQuery UI 组件之后，我们可以查询 UI 组件的状态属性，每个初始化过的 UI 组件都可以调用其方法，调用方法是通过传入方法名称，比如,　调用进程条的 value 方法如下：

```
$( "#elem" ).progressbar( "value" );
```

如果这个方法可以有参数，直接在方法名之后传入参数，比如，设置 value 值为40

```
$( "#elem" ).progressbar( "value", 40 );
```
和前面介绍的 jQuery 方法链一样，jQuery UI 的方法也支持多个方法串接在一起，比如：

```
$( "#elem" )
   .progressbar( "value", 90 )
   .addClass( "almost-done" );
```

##通用方法

对于大多数 jQuery UI 组件来说，有些方法是都支持的，比如：

option 方法

正如前面说的，在 UI 组件初始化之后，如果需要修改一些属性值，可以通过 option 方法，比如，修改 progressbar 的 value 值，

```
$( "#elem" ).progressbar( "option", "value", 30 );
```

注意这和前面调用 value 方法不同，这个例子是想修改配置项 value 为30.
如果需要取得某个配置项的值，则使用不带参数的调用：如：

```
$( "#elem" ).progressbar( "option", "value" );
```

除此之外，如果需要一次修改多个配置项，可以通过传入对象的方法，如：

```
$( "#elem" ).progressbar( "option", {
    value: 100,
    disabled: true
  });
```

diable 方法

这个方法 disable 某个 UI 组件，比如：

```
$( "#elem" ).progressbar( "disable" );
```

这个方法 disable 进程条，并修改其 Style 使其看起来无效。这个方法等同于设置的 disable 属性为 true.

enable 方法

enable UI 组件，比如：

```
$( "#elem" ).progressbar( "enable" );
```

这个方法等同于设置 disable 属性为 false.

destroy 方法

如果你不在需要某个 UI 组件，可以调用 destroy()方法，这将使的对应的 HTML 元素恢复原状（没有使用 jQuery 之前的标记显示）。这也终结 jQuery UI 的生命周期。一旦你终止 UI 组件，你就不能再调用UI组件的方法。如果你删除该 HTML 元素，jQuery 自动终止。

widget 方法

某些 UI 组件创建一个 wrapper 元素或者和原先元素无关联的新元素。在这种情况下，widget 方法返回生成的新元素。对于 Progressbar 来说，没有生成的 HTML 元素，这个方法返回原先的 HTML 元素。

```
$( "#elem" ).progressbar( "widget" );
```

##事件

所有 UI 组件都具有事件来通知其状态发生变化。对于大部分 UI 组件来说，某个事件发生时，事件名以 UI 组件名为前缀。比如当 Progressbar 值发生变化时绑定一个事件处理方法：

```
$( "#elem" ).bind( "progressbarchange", function() {
    alert( "The value has changed!" );
  });
```

每个事件都有对应的回调函数，是作为一个配置项来定义的，因此我们可以直接挂到 Progressbar 的change 回调函数而不要绑定到 Progressbarchange 事件，比如：

```
$( "#elem" ).progressbar({
    change: function() {
      alert( "The value has changed!" );
    }
  });
```

##共有事件

虽然每个 UI 组件支持的事件不同，但 create 事件是每个 UI 组件都支持的，这个事件在 UI 组件创建好后立即触发。
