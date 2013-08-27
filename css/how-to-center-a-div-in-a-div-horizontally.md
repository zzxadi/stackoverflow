__原文地址：__

http://stackoverflow.com/questions/114543/how-to-center-a-div-in-a-div-horizontally

__问题原文：__

如何让在一个div内部的div水平居中？

__问题补充：__

在CSS中如何让在一个`div`内部的`div`水平居中(如果可能的话)?

外部的`div`宽度为100%

```css
<div id="outer" style="width:100%">  
    <div id="inner">Foo foo</div>
</div>
```

__回答1：__

你可以在内部`div`中使用如何样式：

```css
#inner {
	width: 50%;
	margin: 0 auto;
}
```

当然，你不必设置宽度为50%，任意一个小于包含它`div`宽度值都可以，真正让它居中的语句是`margin: 0 auto`。

如果你的目标是IE8+，下面的可能会更好些：

```css
#inner {
	display: table;
	margin: 0 auto;
}
```

它不需要设置具体的宽度值也会使内部的元素水平居中。

__本人理解：__

学习CSS很基础的一个问题是，如何让元素水平居中，网上有很多处理各方面的方法，由于本人CSS知识实在一般，也不会处理各种浏览器兼容性，从来都是使用这个方法。