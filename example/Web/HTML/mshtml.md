[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: MSHTML

```aardio aardio
//MSHTML
import string.html;
import console;

import web.mshtml;
var htmlDoc = web.mshtml();

/*
string.xml 的确是化繁为简�?简洁嘛，有时候也是一种缺点，任何优点从另一面看都是缺点�?如果要做加法，要功能多，这就可以使用强大�?MSHTML 了�?*/
htmlDoc.html=  /*
<!doctype html>
<html>
  <head></head>
  <body>
    <table id="container"><tr><td class="tab_time tab_time102540630" rowspan="1">06:30</td></tr></table>
    <pre>
      string.xml 的确是化繁为简�?简洁嘛，有时候也是一种缺点，任何优点从另一面看都是缺点�?如果要做加法，要功能多，这就可以使用强大�?MSHTML 了�?    </pre>
  </body>
</html>
*/

var body = htmlDoc.querySelector("body");

for i,ele in htmlDoc.eachAll() {
    console.log(i,ele.outerHTML)
}

console.more(,true);

var ret =  htmlDoc.jQuery("body")[0]
console.log( ret.innerText )

console.pause()

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/HTML/mshtml.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/HTML/mshtml.md')

