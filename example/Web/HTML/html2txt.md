[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: HTML 转文�?
```aardio aardio
//HTML 转文�?import console;
import inet.http;
var html = inet.http().get("http://www.aardio.com")

import string.html;
txt = string.html.toText(html);

console.log( txt )
console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/HTML/html2txt.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/HTML/html2txt.md')
