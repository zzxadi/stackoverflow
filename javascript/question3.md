__原文地址：__

http://stackoverflow.com/questions/1335851/what-does-use-strict-do-in-javascript-and-what-is-the-reasoning-behind-it

__问题原文：__

"严格模式"在JavaScript有什么用，背后的原因又是什么呢？

__问题补充：__

最近，我在[老道](http://www.crockford.com/)的[JSLint](http://www.jslint.com/)运行JavaScript，结果抛出如下错误:

> Problem at line 1 character 1: Missing "use strict" statement.

经过搜索，我了解到有些人在他们的JavaScript中添加"use strict"。一经我添加了，错误就没出现了。然而，Google并没有告诉我太多关于“use strict”的内容。
毫无疑问的是它和浏览器怎样解析JavaScript有关，但是我不知道它会引起什么。

所以“use strict”是什么，它意味着什么？

是现在有浏览器支持“use strict"还是它是为了以后使用？

__回答1：__

你也许会对这篇文章感兴趣：[John Resig - ECMAScript 5 Strict Mode, JSON, and More](http://ejohn.org/blog/ecmascript-5-strict-mode-json-and-more/)

引用相关部分：

> 严格模式是ECMAScript 5的一个行特性，允许你把它放在在程序或函数中在严格环境中，严格环境会阻止某些行>为也会抛出更多的异常

和

> 严格模式会在下面几个方面帮到你
  * 捕获某些代码不合理处，抛出异常
  * 当执行不安全的行为会阻止或者抛出异常(比如全局对象)
  * 消除使人迷惑或者的特性

你可以在整个文件使用”严格模式“，或者在某个指定函数( _仍然引用自JoHn Resig's文章_)
```js
// Non-strict code...

(function(){
  "use strict";

  // Define your library strictly...
})();

// Non-strict code... 
```
它说不定会很有帮助在你混合老代码和新代码:-)

所以，我想它很像在Perl中使用的"use strict"(这就是名字的来源？):"use strict"通过检查更多的可能导致破坏的东西来使你犯更少的错误

__本人理解:__

虽然知道，但是基本没有使用过，本来这个也不难，推荐阮一峰的一篇文章[Javascript 严格模式详解](http://www.ruanyifeng.com/blog/2013/01/javascript_strict_mode.html)