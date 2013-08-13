__原文地址：__

http://stackoverflow.com/questions/503093/how-can-i-make-a-redirect-page-in-jquery-javascript

__问题原文：__

在jQuery/JavaScript中如何跳转?

__问题补充：__

在jQuery中如何让用户从一个页面跳转到另一个页面？

__回答1：__

不需要jQuery，`window.location.replace(...)`是模拟HTTP跳转最好的方式。

它比`window.location.href`要更好些，因为`replace()`不会把先前的页面放到历史会话中，也就是说用户后退按钮失效，如果你想模拟点击了链接，用`location.href`，要是你想模拟HTTP跳转，用`location.replace`。

_例如_
```js
// 类似HTTP跳转
window.location.replace("http://stackoverflow.com");

// 类似点击链接
window.location.href = "http://stackoverflow.com";
```

__本人理解:__

这是一个很简单但基本很少去注意的细节，location.replace()，多数人都看过，但基本没用过，更不会注意跳转还有这点区别。