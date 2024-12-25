[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: COM 接口 - 免注册调用远程桌面控�?
```aardio aardio
//COM 接口 - 免注册调用远程桌面控�?import win.ui;
/*DSG{{*/
var winform = win.form(text="远程桌面客户�?;right=599;bottom=799)
winform.add()
/*}}*/

winform.onEraseBkgnd = lambda() 0;
winform.show();

import com.lite;
var dll = com.lite("MsTscAx.dll");

//如果不是内存 DLL 可以省略参数@2里指定的类名( aardio 会自动获�?
var tsc = dll.createEmbedEx(winform,"{7cacbd7b-0d99-468f-ac33-22e495c0afe5}")

//响应远程桌面事件,控件容器对象是默认的事件监听对象
tsc.OnDisconnected = function(discReason){
    select (discReason)  {
        case 2{
            winform.msgbox("已注销登录");
        }
        else{
            winform.msgbox("远程连接失败");
        }
    }
}

//设置远程登录参数 https://docs.microsoft.com/en-us/windows/win32/termserv/mstscax
tsc.Server = "服务器地址";
tsc.UserName = "登录用户�?;
tsc.AdvancedSettings2.ClearTextPassword = "登录密码"; //保存密码可省�?tsc.AdvancedSettings2.EnableCredSspSupport = true; //启用凭据安全服务提供程序(CredSSP)

tsc.AdvancedSettings2.RDPPort = 3389; //端口
tsc.AdvancedSettings2.RedirectPrinters = false; //取消共享打印
tsc.AdvancedSettings2.RedirectDrives = true; //允许共享磁盘
tsc.AdvancedSettings2.SmartSizing = true; //自动调整大小
tsc.DesktopWidth = "800" //桌面宽度
tsc.DesktopHeight = "600"; //桌面高度
tsc.FullScreen = false;//是否全屏
tsc.FullScreenTitle = winform.text;//全屏标题
tsc.ColorDepth = 32;//32位颜�?tsc.ConnectingText = "正在连接......"
tsc.Connect(); //连接

win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/COM/RegFree/MsTscAx.md)

