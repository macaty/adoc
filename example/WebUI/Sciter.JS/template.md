[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: Sciter 使用 aardio 模板语法

```aardio aardio
//模板语法
import win.ui;
/*DSG{{*/
var winform = win.form(text="Sciter 使用 aardio 模板语法";right=1014;bottom=523)
winform.add()
/*}}*/

import web.sciter;
var sciter = web.sciter( winform );

/*
web.sciter 支持 aardio 模板语法�?https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.html

html,js 等都可以直接加载 *.aardio 代码,例如�?aardio 工程里可以直接写:

sciter.go("/res/index.aardio",{
    name = "这里可以指定模板参数,网页中可�?request.get["name"] 访问参数或用 ... 直接接收参数"
})
*/

sciter.html = /**
<!doctype html>
 <html><head><meta charset="utf-8"><title>帮助页面</title></head>
 <body>当前时间 <? = time() ?>

</body></html>
**/

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/template.md)

