[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: API 钩子

```aardio aardio
//API 钩子
//API 钩子就像插队，大家都插队这世界就乱套了，请不要滥用�?
//当前线程 API 钩子
import raw.apiHook;
var hookMessageBoxW = raw.apiHook(
    "user32.dll",
    "MessageBoxW",
    "int(int,ustring,ustring,int)",
    function(hwnd,text,caption,flag){
        //可选用 owner.callApi 调用原始�?API 函数�?        owner.callApi(hwnd, text, "API Hook: " + caption, flag)
        return true;
    }
).install();

//调用 API
::User32.MessageBox(0,"内容","标题",0);

//卸载钩子，不卸载就好比插完队还不肯让出来�?hookMessageBoxW.unInstall();

//多线�?API 钩子
import thread.apiHook;
var hookGetCursorPos = thread.apiHook(
    "user32.dll",
    "GetCursorPos",
    "bool(pointer lpPoint )",
    function( lpPoint ){
        //可选用 owner.callApi 调用原始�?API 函数�?        owner.callApi(lpPoint);

        //猜一猜去掉下面这句，结果有什么不同？�?        return true;

        //钩子中结构体指针参数应当直接传指�?        //可用 raw.mixin 向结构体结针复制数据而不改变原来的指针地址�?        raw.mixin( lpPoint,{
                int x = 123;
                int y = 456
        } );

        return true;
    }
).install();

//调用 API
var point = ::POINT();
::User32.GetCursorPos(point);

import win.dlg.message;
win.dlg.message().info( "x=%d,y=%d",,point.x,point.y );

//卸载钩子，不卸载就好比插完队还不肯让出来
hookGetCursorPos.unInstall();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/aardio/Raw/raw.apiHook.md)

