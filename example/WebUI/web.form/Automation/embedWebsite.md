[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 修改网站页面

```aardio aardio
//修改网站页面
import win.ui;
import web.form;
/*DSG{{*/
var winform = win.form(text="aardio form";right=713;bottom=477;scroll=1)
winform.add()
/*}}*/

//创建web窗体
var wb = web.form( winform  );
wb.noScriptErr=true;

wb.BeforeNavigate2=function( pDisp, url, Flags, TargetFrameName, PostData, Headers, Cancel ) {

    //隐藏wb窗口 也可以考虑将网页放在框架中,在载入时将框架隐�?修改完成后显示框�?    winform.bgcolor = 0xFFFFFF
    win.show(wb.hwndEmbedding,false)

    //创建异步延时函数(这样可以先退出BeforeNavigate2,再执行下面的代码)
    winform.setTimeout(
        function(){
            var qEle = wb.waitQueryEles( { src = "aardio.*\.png" },3000);
            qEle.style.display = "none"
            qEle.outerHTML = ""
            win.show(wb.hwndEmbedding,true)
        },1
    )
}

wb.go("http://bbs.aardio.com/")
winform.show()

win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/web.form/Automation/embedWebsite.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/web.form/Automation/embedWebsite.md')

