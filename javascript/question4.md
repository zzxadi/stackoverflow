__ԭ�ĵ�ַ��__

http://stackoverflow.com/questions/503093/how-can-i-make-a-redirect-page-in-jquery-javascript

__����ԭ�ģ�__

��jQuery/JavaScript�������ת?

__���ⲹ�䣺__

��jQuery��������û���һ��ҳ����ת����һ��ҳ�棿

__�ش�1��__

����ҪjQuery��`window.location.replace(...)`��ģ��HTTP��ת��õķ�ʽ��

����`window.location.href`Ҫ����Щ����Ϊ`replace()`�������ǰ��ҳ��ŵ���ʷ�Ự�У�Ҳ����˵�û����˰�ťʧЧ���������ģ���������ӣ���`location.href`��Ҫ������ģ��HTTP��ת����`location.replace`��

_����_
```js
// ����HTTP��ת
window.location.replace("http://stackoverflow.com");

// ���Ƶ������
window.location.href = "http://stackoverflow.com";
```

__�������:__

����һ���ܼ򵥵���������ȥע���ϸ�ڣ�location.replace()�������˶�������������û�ù���������ע����ת�����������