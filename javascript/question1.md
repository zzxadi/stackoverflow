__原文地址：__
http://stackoverflow.com/questions/901115/how-can-i-get-query-string-values

__问题原文：__
如何得到[查询字符串](http://en.wikipedia.org/wiki/Query_string)的值?  

__问题补充：__
有没有一种方式不用插件便取得查询字符串的值通过jQuery(或者不)?如果有，怎么做呢，如果没有那些插件值得推荐？

__回答：__
你没有必要为了这个目的使用jQuery，你可以只使用JavaScript
```javascript
function getParameterByName(name) {
    name = name.replace(/[\[]/, "\\\[").replace(/[\]]/, "\\\]");
    var regex = new RegExp("[\\?&]" + name + "=([^&#]*)"),
        results = regex.exec(location.search);
    return results == null ? "" : decodeURIComponent(results[1].replace(/\+/g, " "));
}
```