__ԭ�ĵ�ַ��__

http://stackoverflow.com/questions/1789945/method-like-string-contains-in-javascript

__����ԭ�ģ�__

JavaScript������String.contains()�ķ���

__���ⲹ�䣺__

��JavaScript������ж�һ���ַ���������һ���ַ�����
��ͨ��������һ��`String.contains()`�����������������û��

<hr>
���£�������������������

����ʹ��`indexof`ʱ��Firefox�ܾ�ִ��JavaScript����

�ҵĴ������£�
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
Firefox���ᵯ������򣬽����`indexof()`�������ܳ������Ѿ��Թ�����`if (test=="test")...`��������Ч��

__�ش�1:__

[indexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf?redirectlocale=en-US&redirectslug=JavaScript%2FReference%2FGlobal_Objects%2FString%2FindexOf)����һ���ַ�������һ���ַ����е�λ�ã����û�ҵ����ͷ���-1.
```js
var s = "foo";
alert(s.indexOf("oo") != -1);
```

__������⣺__
ÿ���˿�ʼѧϰ�¶����ܻ��������Ƶ�С���⣬���£������������ʡ���������һ��ϸ�ĵ����ӣ���Сдû�������������������С������Ī�����


