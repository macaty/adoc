[aardio 文档](../../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: translate

```aardio aardio
import win.ui;
import web.form;
/*DSG{{*/
var winform = win.form( bottom=249;scroll=1;right=349;text="aardio form" )
winform.add(  )
/*}}*/

//创建web窗体
var wb = web.form( winform );

wb.NewWindow2=function( ppDisp, Cancel) {
    /*弹出新窗口以前触�?*/
    winform.setTimeout(
        function(){
            wb.go( wb.translateUrl )
        },1
    )
    return ppDisp, true; /*第二个返回值如果为�?则取消新窗口*/
}

wb.translate = function( url ){
    /*解析URL时触�?*/
    owner.translateUrl = url;
}

//打开目标网站
wb.go("http://www.aardio.com/")
//显示窗体
winform.show()
wb.wait("");//等待指定网址,可以使用模式匹配语法

//进入消息循环
win.loopMessage();
return winform,wb;

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/web.form/Feature/NoPopups/translate.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/web.form/Feature/NoPopups/translate.md')

