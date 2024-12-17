[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口程序 - 分层透明窗口

```aardio aardio
//窗口程序 - 分层透明窗口
import win.ui;
/*DSG{{*/
var winform = win.form(text="分层透明窗口";right=759;bottom=469)
winform.add(
plus={cls="plus";left=67;top=46;right=664;bottom=399;notify=1;repeat="scale";z=1}
)
/*}}*/

import win.ui.layered;
win.ui.layered(winform);

/*
win.ui.layered 创建的分层窗口支�?png 背景图，
分层窗口上可添加 bkplus,plus 控件，其他控件暂不支持�?web.view, web.layout, web.sciter,web.kit …�?等也都可以创建桌面透明窗口�?*/

import inet.http;
winform.plus.skin(
    background = {
        default = "https://download.aardio.com/demo/images/rose.png";
        hover = 0x6600FF33;
    }
)

winform.plus.oncommand = function(id,event){
    winform.close();
}

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Basics/layered.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Basics/layered.md')

