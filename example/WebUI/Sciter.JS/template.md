[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: Sciter 浣跨敤 aardio 妯℃澘璇硶

```aardio aardio
//妯℃澘璇硶
import win.ui;
/*DSG{{*/
var winform = win.form(text="Sciter 浣跨敤 aardio 妯℃澘璇硶";right=1014;bottom=523)
winform.add()
/*}}*/

import web.sciter;
var sciter = web.sciter( winform );

/*
web.sciter 鏀寔 aardio 妯℃澘璇硶锛?https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.html

html,js 绛夐兘鍙互鐩存帴鍔犺浇 *.aardio 浠ｇ爜,渚嬪鍦?aardio 宸ョ▼閲屽彲浠ョ洿鎺ュ啓:

sciter.go("/res/index.aardio",{
    name = "杩欓噷鍙互鎸囧畾妯℃澘鍙傛暟,缃戦〉涓彲鐢?request.get["name"] 璁块棶鍙傛暟鎴栫敤 ... 鐩存帴鎺ユ敹鍙傛暟"
})
*/

sciter.html = /**
<!doctype html>
 <html><head><meta charset="utf-8"><title>甯姪椤甸潰</title></head>
 <body>褰撳墠鏃堕棿 <? = time() ?>

</body></html>
**/

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/template.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/template.md')

