[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 婊戝昂鎺т欢鎻愮ず

```aardio aardio
//婊戝昂鎺т欢鎻愮ず
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

//鑷粯- 寮鸿绉婚櫎鑾峰緱鐒︾偣鍚庢樉绀虹殑铏氱嚎妗?winform.trackbar.onnotify = function(id,code,ptr){
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Tooltip/trackbar.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Tooltip/trackbar.md')

