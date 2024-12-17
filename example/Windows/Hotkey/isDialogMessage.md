[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 对话框默认快捷键 ESC、Enter�?
```aardio aardio
//ESC、Enter
import win.ui;
/*DSG{{*/
var winform = win.form(text="对话框默认快捷键 ESC、Enter�?;right=759;bottom=469)
winform.add()
/*}}*/

winform.onCancel = function(){
    winform.msgbox("你按了ESC");
    winform.close();
}

winform.onOk = function(){
    winform.msgbox("你按了Enter");
}

/*
窗口会自动检测默认的对话框快捷键�?默认Enter会触发onOk事件，ESC键会触发onCancel事件�?可选如下自定义检测对话框快捷键函�?winform.isDialogMessage
*/
winform.isDialogMessage = function(hwnd,msg){
    if( msg.message == 0x100/*_WM_KEYDOWN*/){

        if(  msg.wParam == 0xD/*_VK_RETURN*/ ){
            //return true;//告诉消息处理函数这是一个快捷键,阻止按键消息继续分发
        }

        if( msg.wParam == 0x1B/*_VK_ESC*/ ){
            //return true;//告诉消息处理函数这是一个快捷键,阻止按键消息继续分发
        }
    }

    //检测并响应默认快捷�?    return win.isDialogMessage(hwnd,msg);
}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Hotkey/isDialogMessage.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Hotkey/isDialogMessage.md')

