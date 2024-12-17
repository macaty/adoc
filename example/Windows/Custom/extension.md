[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口程序 - 使用自定义控件作为宿主窗口创建扩展控�?
```aardio aardio
//窗口程序 - 使用自定义控件作为宿主窗口创建扩展控�?import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=469)
winform.add(
button={cls="button";text="全屏";left=523;top=415;right=630;bottom=460;db=1;dr=1;z=2};
custom={cls="custom";text="自定义控�?;left=17;top=26;right=732;bottom=380;db=1;dl=1;dr=1;dt=1;z=1}
)
/*}}*/

/*
�?aardio 中我们还可以对任何一个窗口、或窗口上的子窗件进行扩展，
这种用法�?aardio 中被大量使用，例如让窗口嵌入浏览器控件，以增加显示网页的功能�?这样的库非常多，例如 web.form,web.view,web.sysView,web.layout,web.sciter,chrome.app  …�?*/
import web.form;
var wb  = web.form( winform.custom )
/*
如果我们想用整个窗体显示网页�?可以这样写： var wb  = web.form( winform )

但如果我们只是希望窗体上某个子窗口显示网页，
我们可以�?web.form 的构造参数中指定子窗口控件，
通常我们会使�?custom �?static 这种简单的控件，因为控件的其他功能通常是多余的�?*/

wb.html = /**
<!doctype html>
<html>
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <style type="text/css">
    html,body{ margin:50; }
    </style>
</head>
<body>这是一个网�?<button id="fullscreen" onclick="external.close()">关闭</button>
**/

wb.external={
    close = function(){ winform.close()}
}

winform.button.oncommand = function(id,event){
    /*
    因为默认�?custom 控件就是 win.form 窗体对象，窗体对象有一个非常好用的全屏函数�?    */
    winform.custom.fullscreen()
}

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Custom/extension.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Custom/extension.md')

