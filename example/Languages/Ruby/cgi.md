[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: Hello World / PHP\_CGI 鏈嶅姟鍣?
```aardio aardio
//Ruby/CGI鏈嶅姟鍣?import win.ui;
/*DSG{{*/
var winform = win.form(text="Hello World / PHP_CGI 鏈嶅姟鍣?;right=759;bottom=469)
winform.add()
/*}}*/

//Ruby 璇硶閫熻 https://quickref.me/zh-CN/docs/ruby.html
var code = /*
require 'cgi'

cgi = CGI.new
puts cgi.header
puts "<html><body>This is a test</body></html>"
*/
string.save("/index.rb",code);

import process.ruby.simpleHttpServer;
var url = process.ruby.simpleHttpServer.startUrl("/index.rb");

import web.form;
var wb = web.form(winform);

wb.go(url);
winform.show();

win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Ruby/cgi.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Ruby/cgi.md')

