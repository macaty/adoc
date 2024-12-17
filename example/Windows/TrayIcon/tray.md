[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 创建托盘图标

```aardio aardio
//创建托盘图标
import win.ui;
import win.ui.menu;
/*DSG{{*/
var winform = win.form(text="托盘图标";left=0;top=0;right=330;bottom=156)
winform.add(
button={cls="button";text="创建托盘图标";left=97;top=37;right=248;bottom=68;z=1}
)
/*}}*/

//下面创建托盘图标
import win.util.tray;
winform.button.oncommand = function(id,event){
    winform.tray = win.util.tray(winform)
    winform.tray.tip = "鼠标提示" //设置鼠标提示

    //注意在单引号包含的转义字符串里只能以 '\n' 表示换行符，其他换行被忽略�?    winform.tray.pop('
Win10 开始由操作系统的『专注』、应用程序的『通知』等设置
决定是否显示模幅提示或折叠消息到通知区。通知消息可使�?dotNet.toastListener 扩展库�?
,"托盘消息通知");
}

winform.onMinimize = function(lParam){
    winform.tray = win.util.tray(winform);
    winform.show(false); //隐藏窗口
    return true;//阻击默认消息传�?取消最小化过程
}

winform.onTrayMessage = {
    [0x205/*_WM_RBUTTONUP*/  ] = function(wParam){
        //弹出托盘菜单以前,一定要前置主窗口中,
        //避免不点击菜单不会消失，父窗口隐藏也要这样做
        win.setForeground(winform.hwnd,true) //参数 2 �?true 避免显示最小化窗口

        /*
        下面创建托盘弹出菜单�?        如果程序要开机启动到托盘，最好在这里创建菜单，在用户点击前不要创建菜单，
        避免系统启动�?DPI 缩放前创建的菜单字体偏小（出现这情况的机率很小）�?        如果不想重复创建菜单最好写到一个库里，然后在这�?import 即可避免上述问题�?        */
        import win.ui.menu;

        winform.popmenu = win.ui.popmenu(winform);//创建弹出菜单
        winform.popmenu.add('&open',function(id){
            //在下面输入菜单响应代�?
        });
        winform.popmenu.add();//分隔�?        winform.popmenu.add('&exit',function(id){ winform.close() })

        winform.popmenu.popup();
        winform.popmenu.close();
    };
    [0x202/*_WM_LBUTTONUP*/] = function(wParam){

    };
    [0x203/*_WM_LBUTTONDBLCLK*/] = function(wParam){

    };
    [0x404/*_PARAM_DESTROY*/] = function(wParam){

    };
    [0x405/*_PARAM_CLICKED*/] = function(wParam){

    };
}

winform.show(true);
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/TrayIcon/tray.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/TrayIcon/tray.md')

