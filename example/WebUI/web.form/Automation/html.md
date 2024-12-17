[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 快速抓取分析网�?
```aardio aardio
//快速抓取网�?import win.ui;
/*DSG{{*/
var winform = win.form(text="快速抓取分析网�?;right=600;bottom=400)
winform.add()
/*}}*/

import web.form;
var wb = web.form( winform ,/*_UIFLAG_*/
    //禁用图片,禁用脚本,禁用ActiveX控件,禁用框架
    ,0 | 0x80/*_DLCTL_NO_SCRIPTS*/ | 0x200/*_DLCTL_NO_RUNACTIVEXCTLS*/ | 0x1000/*_DLCTL_NO_FRAMEDOWNLOAD*/
);

winform.show()

wb.DocumentComplete = function(pDisp,url) {
    if( pDisp == wb.application ){
        winform.text = wb.document.title;
    }
}

do{
    for(i=1;2;1){
        wb.go("http://www.aardio.com");
        wb.wait();

        wb.go("about:...");
        wb.wait();
    }
}while(! winform.msgboxTest("是不是很快？") )

win.loopMessage();
return winform;

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/web.form/Automation/html.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/web.form/Automation/html.md')

