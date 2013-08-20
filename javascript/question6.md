__原文地址：__

http://stackoverflow.com/questions/134845/href-attribute-for-javascript-links-or-javascriptvoid0

__问题原文：__

JavaScript链接中`Href`属性：“#”还是“javascript:void(0)”?

__问题补充：__

当为了运行JavaScript代码创建一个链接，通常有两种写代码的方式，不论哪一种更好呢，不论从功能，页面载于速度，验证等等？

```javascript
<a href="#" onclick="myJsFunc();">Run JavaScript Code</a>
```
or

```javascript
<a href="javascript:void(0)" onclick="myJsFunc();">Run JavaScript Code</a>
```

__回答1:__

我用`javascript:void(0)`

三个原因，鼓励使用#的开发人员不可避免导致在function中返回某些值，类似如下：

```javascript
function doSomething() {
	//Some code
    return false;
}
```
但是他们在onclick中只使用了`doSomething()`而忘记使用`return doSomething()`。

不使用`#`第二个原因是最后的`return false;`如果function出现错误将不会执行，因此开发人员不得不记得适当的在调用的function中处理任何错误。

第三个原因