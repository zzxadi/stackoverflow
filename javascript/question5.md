__原文地址：__

http://stackoverflow.com/questions/1789945/method-like-string-contains-in-javascript

__问题原文：__

JavaScript中类似String.contains()的方法

__问题补充：__

在JavaScript中如何判断一个字符串包含另一个字符串？
我通常会期望一个`String.contains()`方法，但是这里好像没有

<hr>
更新：好像我又有其他问题

当我使用`indexof`时，Firefox拒绝执行JavaScript代码

我的代码如下：
```js
var allLinks = content.document.getElementsByTagName("a");

for (var i=0, il=allLinks.length; i<il; i++) {
    elm = allLinks[i];
    var test = elm.getAttribute("class");
    if (test.indexof("title") !=-1) {
        alert(elm);
        foundLinks++;
    }
}

if (foundLinks === 0) {
    alert("No title class found");
} 
else {
    alert("Found " + foundLinks + " title class");
}
```
Firefox不会弹出警告框，结果是`indexof()`方法可能出错。我已经试过类似`if (test=="test")...`，但是无效。

__回答1:__

[indexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf?redirectlocale=en-US&redirectslug=JavaScript%2FReference%2FGlobal_Objects%2FString%2FindexOf)返回一个字符串在另一个字符串中的位置，如果没找到，就返回-1.
```js
var s = "foo";
alert(s.indexOf("oo") != -1);
```

__本人理解：__
每个人开始学习新东西总会碰到类似的小问题，别害怕，大胆搜索，提问。不过这是一个细心的例子，大小写没分清楚，但经常是这类小问题搞得莫名其妙。


