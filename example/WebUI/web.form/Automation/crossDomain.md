[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 跨域控制框架页面

```aardio aardio
//跨域框架
import win.ui;
/*DSG{{*/
var winform = win.form(text="跨域控制框架页面";right=728;bottom=479)
winform.add(
btnCrossFrame={cls="button";text="点这里演示跨域操作子框架";left=442;top=6;right=673;bottom=37;dr=1;dt=1;z=1}
)
/*}}*/

//创建web窗体
import web.form;
import web.form.util;
var wb = web.form( winform );
wb.noScriptErr = true;

winform.show(true)

var html = /**
<!doctype html>
<html>
<head>
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta charset="utf-8">
</head>
<body style="margin:0px;">
<div  style=" margin:5px;font-size:9pt;">
        下面的框架与父窗口分别位于不同域名下,默认无法跨域控制子框�?br />
        调用 web.form.util.crossDomain() 开启跨域支�?<br />
        所有web窗体函数即可自动支持跨域框架.
</div>
        <iframe name="xDomainFrame"
        src="http://www.aardio.com" frameborder="0" scrolling="yes"
        height="900" width="100%" noresize="noresize">
        </iframe>
</body>
</html>
**/

string.save("/xDomain.html", html)
wb.go("/xDomain.html")
wb.wait();

winform.btnCrossFrame.oncommand = function(id,event){

    //开启跨�?    web.form.util.crossDomain()

    //遍历所有框�?    for(i=1;wb.document.frames.length ){
        var wbFrame = wb.getWebForm(i-1); //将框架转换为web.form对象
        wbFrame.body.innerHTML = "成功跨域,这是写入的内�?
    }

    //关闭跨域功能,非必需
    web.form.util.crossDomain(false)
}

//进入消息循环
win.loopMessage();
return winform,wb;

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/web.form/Automation/crossDomain.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/web.form/Automation/crossDomain.md')

