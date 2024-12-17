[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 用IFrame做的浏览�?
```aardio aardio
//跨域框架实现浏览�?
import win.ui;
/*DSG{{*/
var winform = win.form(text="用IFrame做的浏览�?;right=735;bottom=479;)
winform.add()
/*}}*/

//开启跨�?import web.form.util;
web.form.util.crossDomain()

//创建web窗体
var wb = web.form( winform,0x40000/*_UIFLAG_THEME*/ )
wb.noScriptErr = true;

//自动启用禁用 前进、后退等按�?wb.CommandStateChange=function(cmd,enable) {
    select(cmd) {
        case 0x2/*_CSC_NAVIGATEBACK*/ {
            wb.getEle("btnBack").disabled = !enable
        }
        case 0x1/*_CSC_NAVIGATEFORWARD*/ {
            wb.getEle("btnForward").disabled = !enable
        }
    }
}

wb.html = /**
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
</head>
<body style="overflow:hide; margin:0px; ">
<div id="navBar" style=" margin:5px;">
        <label for="txtUrl">网址</label>
        <input type="text" name="txtUrl" id="txtUrl" value="https://www.aardio.com">
        <input id="btnGo" type="button" onClick="external.go(document.getElementById('txtUrl').value )"  value="打开" />
        <input id="btnRefresh" type="button" onClick="external.refresh()"  value="刷新" />
        <input id="btnBack" type="button" onClick="history.back()"  value="后退" />
        <input id="btnForward" type="button" onClick="history.forward()"  value="前进" />
</div>
        <iframe name="xDomainFrame" src="https://www.aardio.com" frameborder="0" scrolling="yes" height="100%" width="100%" noresize="noresize">
        </iframe>
</body>
</html>
**/
wb.wait();

wbFrame = wb.getWebForm("xDomainFrame")

wb.BeforeNavigate2=function( pDisp, url, Flags, TargetFrameName, PostData, Headers, Cancel ) {
    winform.text = "正在打开 " + url + " ......";

    ele = wb.getEle("txtUrl");
    if(ele){
        ele.value = wbFrame.location;
    }
}
wb.DocumentComplete=function( pDisp, url) {
    winform.text = wbFrame.document.title;
    winform.text = wbFrame.location;

    ele = wb.getEle("txtUrl");
    if(ele){
        ele.value = wbFrame.location;
    }
}

wb.external={
    refresh = function(){
        wbFrame.refresh2()
    }
    go = function(...){
        wbFrame.go(...)
    }
}

winform.show(3/*_SW_MAXIMIZE*/);
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/web.form/Browser/frameBrowser.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/web.form/Browser/frameBrowser.md')

