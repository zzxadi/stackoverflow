__原文地址：__

http://stackoverflow.com/questions/111102/how-do-javascript-closures-work

__问题原文：__

JavaScript闭包如何工作？ 

__问题补充：__

就像爱因斯坦[说过](http://www.searchquotes.com/quotation/If_you_can%27t_explain_it_to_a_six_year_old,_you_don%27t_understand_it_yourself./333069/)：“如果一件事情你不能向6岁小孩解释清楚，那么你自己并未真正的理解它”，然而，我试图向一个27岁的朋友解释JavaScript闭包结果失败了。

你会怎样向一个对那种话题感兴趣6岁小孩解释清楚呢？

__回答1：__

当你看到function关键字在另一个函数里，内部的函数可以访问外部函数的变量
```javascript
function foo(x) {
  var tmp = 3;
  function bar(y) {
    alert(x + y + (++tmp));
  }
  bar(10);
}
foo(2)
```
这个会一直弹出16，因为`bar`可以访问`foo`的形参`x`和内部变量`tmp`。

那不是闭包，只有当返回内部函数的时候才是闭包，内部函数会在返回前提前结束`foo`中变量的生命周期
```js
function foo(x) {
  var tmp = 3;
  return function (y) {
    alert(x + y + (++tmp));
  }
}
var bar = foo(2); // bar is now a closure.
bar(10);
```
上面的函数也会弹出16，因为`bar`仍然可以引用到`x`和`tmp`，尽管它不在它的直接内部作用域中

然而，由于`tmp`仍然被内部`bar`闭包把持着，它仍然会递增。你每调用一次`bar`，他就会自增一次。

创建超过一个闭包函数是可能的，既可以通过返回闭包列表也可以把他们设为全局变量，所有的这些都会引用相同的`x`和`tmp`，它们不会复制为自己的变量。

[你]:这个太迷人了，告诉我更多吧！

这里的数字`x`是一个基本数值，和JS其他的基本类型一样，当`foo`被调用时，`x`会被复制来作为`foo`的形参。

另一方面，JavaScript在处理对象使用的是引用，也就是说，`foo`作为一个对象被调用，返回的闭包是原始对象的 __引用__！
```js
function foo(x) {
  var tmp = 3;
  return function (y) {
    alert(x + y + tmp);
    x.memb = x.memb ? x.memb + 1 : 1;
    alert(x.memb);
  }
}
var age = new Number(2);
var bar = foo(age); // bar is now a closure referencing age.
bar(10);
```
就像期望的，每调用一次`bar(10)`就会让`x.memb`自增一次。可能不像你期望的是`x`和`age`引用的是同一个对象！
再次调用`bar`后，age.memb值将会变成2！这个引用是导致HTML对象内存泄露的基本原因。

__本人理解:__

闭包对初学者总是很难理解，因为一搜往往是一大堆概念，当时可能理解了，过后就忘了，我对闭包有更深入的了解来源于这篇文章[深入理解JavaScript闭包(closure)](http://www.felixwoo.com/archives/247) ，我也强烈推荐一下。