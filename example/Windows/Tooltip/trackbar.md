[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 滑尺控件提示

```aardio aardio
//滑尺控件提示
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=469)
winform.add(
trackbar={cls="trackbar";left=282;top=286;right=536;bottom=316;max=100;min=0;z=1}
)
/*}}*/

/**
import win.ui.tooltip;
var hwndTooltipCtrl = winform.trackbar.sendMessage(0x41E/*_TBM_GETTOOLTIPS*/,0,0);
var tooltipCtrl = win.ui.tooltip(winform,hwndTooltipCtrl);

winform.trackbar.oncommand = function(id,event,pos){
    var toolInfo = tooltipCtrl.getCurrentTool();
    if(toolInfo)toolInfo.setText( tostring(pos / 10) );
}
**/

winform.trackbar.oncommand = function(id,event,pos){
    winform.trackbar.tooltip = pos / 10;
}

//自绘- 强行移除获得焦点后显示的虚线�?winform.trackbar.onnotify = function(id,code,ptr){
    if( code == 0xFFFFFFF4/*_NM_CUSTOMDRAW*/ ){
        var lvcd = winform.trackbar.getNotifyCustomDraw(code,ptr);
        if( lvcd.dwDrawStage == 1/*_CDDS_PREPAINT*/ ){
            lvcd.uItemState = lvcd.uItemState &  ~0x10/*_CDIS_FOCUS*/;
            lvcd.update();
        }
    }
}

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Tooltip/trackbar.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Tooltip/trackbar.md')

