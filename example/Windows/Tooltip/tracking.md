[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 提示控件 / 跟踪模式 / 启用超链�?
```aardio aardio
//跟踪超链�?import win.ui;
/*DSG{{*/
var winform = win.form(text="提示控件 / 跟踪模式 / 启用超链�?;right=759;bottom=469)
winform.add(
button={cls="button";text="点这里显示提示控�?;left=176;top=156;right=404;bottom=227;z=1}
)
/*}}*/

import win.ui.tooltip;
var tooltipCtrl = win.ui.tooltip.tracking(winform);
tooltipCtrl.setInfo("提示标题");//在这里指定标题（自动启用关闭按钮），
//提示控件只有如上指定所有者窗口、并设置标题（启用关闭按钮）才能响应提示中的超链接点击事�?
import process;
tooltipCtrl.onHyperlinkClick = function(href,title){
    process.openUrl(href);
}

var toolInfo = tooltipCtrl.addTrackingTool(winform.button);
winform.button.oncommand = function(id,event){
    var x,y,cx,cy = winform.button.getPos(true)
    toolInfo.setText(`点链接试试：<a href="https://www.aardio.com">aardio.com</a>`).trackPopup(true,x+20,y+cy);
    tooltipCtrl.capture = true;
}

tooltipCtrl.wndproc = function(hwnd,message,wParam,lParam){
    if(message==0x201/*_WM_LBUTTONDOWN*/){
        if(!tooltipCtrl.ptInClientRect(lParam)){
            tooltipCtrl.popup(false);
        }
    }
}

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Tooltip/tracking.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Tooltip/tracking.md')

