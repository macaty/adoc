[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: Hello World / PHP\_CGI 服务�?
```aardio aardio
//Ruby/CGI服务�?import win.ui;
/*DSG{{*/
var winform = win.form(text="Hello World / PHP_CGI 服务�?;right=759;bottom=469)
winform.add()
/*}}*/

//Ruby 语法速览 https://quickref.me/zh-CN/docs/ruby.html
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

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Ruby/cgi.md)

