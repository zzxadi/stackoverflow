__原文地址：__

http://stackoverflow.com/questions/901115/how-can-i-get-query-string-values

__问题原文：__

如何得到[查询字符串](http://en.wikipedia.org/wiki/Query_string)的值?  

__问题补充：__

有没有一种方式不用插件便取得查询字符串的值通过jQuery(或者不)?如果有，怎么做呢，如果没有那些插件值得推荐？

__回答1：__

你没有必要为了这个目的使用jQuery，你可以只使用JavaScript
```js
function getParameterByName(name) {
    name = name.replace(/[\[]/, "\\\[").replace(/[\]]/, "\\\]");
    var regex = new RegExp("[\\?&]" + name + "=([^&#]*)"),
        results = regex.exec(location.search);
    return results == null ? "" : decodeURIComponent(results[1].replace(/\+/g, " "));
}
```

__本人理解:__

在项目中获取URL上的查询字符串是很常见的操作，比如有一段地址:<code>http://www.stackoverflow.com?username=zzxadi&sex=male&age=24</code>,要取得sex的值，怎么办呢？
这是我项目中使用的代码
```js
function getUrlParam(sName)
{	
	if(sName)
	{
		var sValue='';
		var re= new RegExp("\\b"+sName+"\\b=([^&=]+)");
		var st=null;
		st=window.location.search.match(re);
		if(st&&st.length==2)
		{	
			st[1]=st[1].replace(/^\s*|\s*$/g,'');
			sValue=st[1];
		}
		return sValue;
	}
	
   return "";

}
```

