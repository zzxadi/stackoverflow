__ԭ�ĵ�ַ��__
http://stackoverflow.com/questions/111102/how-do-javascript-closures-work

__����ԭ�ģ�__
JavaScript�հ���ι����� 

__���ⲹ�䣺__
������˹̹[˵��](http://www.searchquotes.com/quotation/If_you_can%27t_explain_it_to_a_six_year_old,_you_don%27t_understand_it_yourself./333069/)�������һ�������㲻����6��С�������������ô���Լ���δ���������������Ȼ��������ͼ��һ��27������ѽ���JavaScript�հ����ʧ���ˡ�

���������һ�������ֻ������Ȥ6��С����������أ�

__�ش�1��__
���㿴��function�ؼ�������һ��������ڲ��ĺ������Է����ⲿ�����ı���
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
�����һֱ����16����Ϊ<code>bar</code>���Է���<code>foo</code>���β�<code>x</code>���ڲ�����<code>tmp</code>��

�ǲ��Ǳհ���ֻ�е������ڲ�������ʱ����Ǳհ����ڲ��������ڷ���ǰ��ǰ����<code>foo</code>�б�������������
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
����ĺ���Ҳ�ᵯ��16����Ϊ<code>bar</code>��Ȼ�������õ�<code>x</code>��<code>tmp</code>����������������ֱ���ڲ���������

Ȼ��������<code>tmp</code>��Ȼ���ڲ�<code>bar</code>�հ��ѳ��ţ�����Ȼ���������ÿ����һ��<code>bar</code>�����ͻ�����һ�Ρ�

��������һ���հ������ǿ��ܵģ��ȿ���ͨ�����رհ��б�Ҳ���԰�������Ϊȫ�ֱ��������е���Щ����������ͬ��<code>x</code>��<code>tmp</code>�����ǲ��Ḵ��Ϊ�Լ��ı�����

[��]:���̫�����ˣ������Ҹ���ɣ�

���������<code>x</code>��һ��������ֵ����JS�����Ļ�������һ������<code>foo</code>������ʱ��<code>x</code>�ᱻ��������Ϊ<code>foo</code>���βΡ�

��һ���棬JavaScript�ڴ������ʹ�õ������ã�Ҳ����˵��<code>foo</code>��Ϊһ�����󱻵��ã����صıհ���ԭʼ����� __����__��
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
���������ģ�ÿ����һ��<code>bar(10)</code>�ͻ���<code>x.memb</code>����һ�Ρ����ܲ�������������<code>x</code>��<code>age</code>���õ���ͬһ������
�ٴε���<code>bar</code>��age.membֵ������2����������ǵ���HTML�����ڴ�й¶�Ļ���ԭ��

__�������:__
�հ��Գ�ѧ�����Ǻ�����⣬��Ϊһ��������һ��Ѹ����ʱ��������ˣ���������ˣ��ҶԱհ��и�������˽���Դ����ƪ����[�������JavaScript�հ�(closure)](http://www.felixwoo.com/archives/247) ����Ҳǿ���Ƽ�һ�¡�