[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: RUNAS//网卡切换

```aardio aardio
//RUNAS//网卡切换
import win.ui;
/*DSG{{*/
var winform = win.form(text="网络连接";right=537;bottom=206)
winform.add()
/*}}*/

if(!_STUDIO_INVOKED){
    if(!_ARGV.task){
        import sys.runAsTask;
        var task = sys.runAsTask("MyNetworkManager","网卡自动切换程序");
        task.register("/task");

        win.msgbox("本程序已设置为登录时自动以管理权限运行（无确认对话框�?);
        return;
    }
}

import inet.connView;
var wb = inet.connView(winform);
wb.shellFolderSelectionChanged = function(itemPath,itemName) {

}

var iconNetWork = ::User32.LoadIconP(::Shell32,18);
winform.setIcon(iconNetWork);

import win.util.tray;
winform.tray = win.util.tray(winform,iconNetWork);

winform.onMinimize = function(lParam){
    winform.show(false); //隐藏窗口
    return true;//阻击默认消息传�?取消最小化过程
}

import win.ui.menu;
import sys.networkCards;
import com.wmi;

reloadNetworkAdapters = function(){
    winform.popmenu = win.ui.popmenu(winform);

    var adAct,adActMenuId;
    for networkCard in sys.networkCards.each(){
        var adCur = com.wmi.get("SELECT * FROM Win32_NetworkAdapter WHERE NetConnectionId =@netConnectionId",networkCard)
        if(!adCur){
            continue;
        }

        var idCur;
        idCur = winform.popmenu.add('切换到：' + networkCard.netConnectionId,function(){
            if(adAct){
                //有些驱动或硬件有问题的网卡，可能要用 process.devcon.disable() 才能禁用
                adAct.Disable(); //禁用网卡
                winform.popmenu.check(adActMenuId,false,0/*_MF_BYCOMMAND*/);

                if(adAct == adCur){
                    adAct = null;
                    adActMenuId = null;
                    return;
                }
            }

            adAct = adCur;
            adCur.Enable(); //启用网卡

            adActMenuId = idCur;
            winform.popmenu.check(adActMenuId,true,0/*_MF_BYCOMMAND*/);
        });

        if(adCur.NetEnabled){
             adAct = adCur;
             adActMenuId = idCur;
             winform.popmenu.check(idCur,true,0/*_MF_BYCOMMAND*/);
        }
    }

    winform.popmenu.add();
    winform.popmenu.add('浏览网络连接…�?,function(){
        import process;
        process.explore("shell:::{7007ACC7-3202-11D1-AAD2-00805FC1270E}");
    });
    winform.popmenu.add('退�?,function(){ winform.close() });
}

winform.wndproc = {
    [0xACCF/*_WM_TRAYMESSAGE*/ ] = function(hwnd,message,wParam,lParam){
        if( lParam = 0x205/*_WM_RBUTTONUP*/ ){
            //弹出托盘菜单以前,一定要前置主窗口中,不然不点击菜单不会消�?            win.setForeground(winform.hwnd)
            winform.popmenu.popup()
        }
        elseif( lParam = 0x203/*_WM_LBUTTONDBLCLK*/ ){
            winform.show(true);
        }
    }
}

reloadNetworkAdapters();
winform.show(true);
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/Manage/connections.md)

