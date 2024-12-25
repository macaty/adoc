[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 检测网络状�?
```aardio aardio
//断网检�?import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="检测网络状�?;right=759;bottom=469;bgcolor=16777215;max=false)
winform.add(
btnOpenNetworkConnections={cls="button";text="打开网络连接";left=226;top=339;right=463;bottom=398;bgcolor=16777215;note="打开 控制面板 / 网卡列表";z=3};
lbStatus={cls="plus";left=249;top=57;right=678;bottom=98;align="left";font=LOGFONT(h=-19);transparent=1;z=2};
plusNetworkStatus={cls="plus";text="网络已连�?;left=66;top=57;right=242;bottom=98;align="left";color=32768;disabled=1;font=LOGFONT(h=-19);iconStyle={align="left";font=LOGFONT(h=-27;name='FontAwesome');padding={left=9}};iconText='\uF205';textPadding={left=49};z=1}
)
/*}}*/

import wsock.networkChange;
wsock.networkChange.wait(winform).onNetworkChanged = function(){

    //网络状态变更触发此回调
    winform.plusNetworkStatus.checked = wsock.tcp.client.test();

    winform.lbStatus.disabledText = {"�?;"�?;"�?;"�?;"�?;"�?;text=' '}
    winform.lbStatus.onNetworkChanged();
}

import inet.ras;
import win.debounce;
winform.lbStatus.onNetworkChanged = win.debounce( function(){
    winform.lbStatus.disabledText = null;

    /*
    win.debounce 可以避免短时间内不必要地连续调用此函数�?    也可以延时调�?inet.ras.isAlive 以获取刷新后的状态�?    */
    var wan,lan = inet.ras.isAlive();
    if( lan ) winform.lbStatus.text = "已有网卡建立了局域网连接";
    else if( wan ) winform.lbStatus.text = "已有网卡建立了广域网连接";
    else winform.lbStatus.text = "没有联网";
},1000);

winform.plusNetworkStatus.skin({
    text="网络已断开";
    color = {
        default = 0xFFFF0000;
        disabled = 0xFFFF0000;
    };

    checked = {
        text = "网络已连�?;
        color = {
            default = 0xFF008000;
        };
    }
});

import process;
winform.btnOpenNetworkConnections.oncommand = function(id,event){
    process.explore("shell:::{7007ACC7-3202-11D1-AAD2-00805FC1270E}");
}

winform.onNetworkChanged();
winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/Manage/isAlive.md)

