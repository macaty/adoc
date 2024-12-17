[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口程序 - 消息回调

```aardio aardio
//窗口程序 - 消息回调
import win.ui;
import win.ui.atom;
/*DSG{{*/
var winform = win.form(text="aardio form";right=758;bottom=423)
winform.add(
btnMessageView={cls="button";text="打开 Windows 消息大全";left=509;top=354;right=702;bottom=400;z=3};
btnSendMessage={cls="button";text="发送消�?;left=358;top=354;right=485;bottom=400;z=1};
edit={cls="edit";left=37;top=33;right=732;bottom=342;edge=1;multiline=1;z=2}
)
/*}}*/

/*
窗体或控件都可以定义 wndproc 函数处理窗口消息�?每次定义 wndproc 都会增加新的窗口处理函数，不会替换或覆盖之前的窗口消息回调函数�?winform.wndproc 最后一次定义的回调函数总是最先被调用�?
winform.tailWndproc �?wndproc 的作用相同，
但总是会最后调用最后赋值给tailWndproc的回调函数�?
wndproc 的值也可以是一个表，表的键是要处理的消息，值是处理该消息的回调函数�?wndproc 的值为表时，该表只会保留同一消息ID最后一次设置的回调函数�?*/
winform.wndproc = function(hwnd,message,wParam,lParam){
    if(message==0xD/*_WM_GETTEXT*/){
        var wstr = '这是通过窗口消息返回的窗口标�?u;
        if(wParam>#wstr){
            raw.copy(topointer(lParam),wstr);
            return #wstr/2;
        }
    }

    //无返回�?或返�?null )则继续调用默认回调函�?}

/*
可使用以下函数发送消息：
::User32.SendMessage(hwnd,message,wParam,lParam)
::User32.PostMessage(hwnd,message,wParam,lParam)
�?参数 hwnd 为目标窗口句柄，参数 message 为消息ID
wParam,lParam 的用法每个消息可能不一样，可查阅相关消息文�?*/
winform.btnSendMessage.oncommand = function(id,event){
    var ret,text = ::User32.SendMessage(winform.hwnd,0xD/*_WM_GETTEXT*/,200,{WORD value[100]});
    winform.edit.text = string.str( text.value );
}

winform.btnMessageView.oncommand = function(id,event){
    import ide;
    ide.createProcess("~\tools\GUI\message.aardio");
}

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Basics/wndproc..md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Basics/wndproc..md')

