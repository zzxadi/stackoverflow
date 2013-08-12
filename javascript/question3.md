__ԭ�ĵ�ַ��__

http://stackoverflow.com/questions/1335851/what-does-use-strict-do-in-javascript-and-what-is-the-reasoning-behind-it

__����ԭ�ģ�__

"�ϸ�ģʽ"��JavaScript��ʲô�ã������ԭ������ʲô�أ�

__���ⲹ�䣺__

���������[�ϵ�](http://www.crockford.com/)��[JSLint](http://www.jslint.com/)����JavaScript������׳����´���:

> Problem at line 1 character 1: Missing "use strict" statement.

�������������˽⵽��Щ�������ǵ�JavaScript�����"use strict"��һ��������ˣ������û�����ˡ�Ȼ����Google��û�и�����̫����ڡ�use strict�������ݡ�
�������ʵ��������������������JavaScript�йأ������Ҳ�֪����������ʲô��

���ԡ�use strict����ʲô������ζ��ʲô��

�������������֧�֡�use strict"��������Ϊ���Ժ�ʹ�ã�

__�ش�1��__

��Ҳ������ƪ���¸���Ȥ��[John Resig - ECMAScript 5 Strict Mode, JSON, and More](http://ejohn.org/blog/ecmascript-5-strict-mode-json-and-more/)

������ز��֣�

> �ϸ�ģʽ��ECMAScript 5��һ�������ԣ���������������ڳ�����������ϸ񻷾��У��ϸ񻷾�����ֹĳЩ��>ΪҲ���׳�������쳣

��

> �ϸ�ģʽ�������漸������ﵽ��
  * ����ĳЩ���벻�������׳��쳣
  * ��ִ�в���ȫ����Ϊ����ֹ�����׳��쳣(����ȫ�ֶ���)
  * ����ʹ���Ի���ߵ�����

������������ļ�ʹ�á��ϸ�ģʽ����������ĳ��ָ������( _��Ȼ������JoHn Resig's����_)
```js
// Non-strict code...

(function(){
  "use strict";

  // Define your library strictly...
})();

// Non-strict code... 
```
��˵��������а����������ϴ�����´���:-)

���ԣ�������������Perl��ʹ�õ�"use strict"(��������ֵ���Դ��):"use strict"ͨ��������Ŀ��ܵ����ƻ��Ķ�����ʹ�㷸���ٵĴ���

__�������:__

��Ȼ֪�������ǻ���û��ʹ�ù����������Ҳ���ѣ��Ƽ���һ���һƪ����[Javascript �ϸ�ģʽ���](http://www.ruanyifeng.com/blog/2013/01/javascript_strict_mode.html)