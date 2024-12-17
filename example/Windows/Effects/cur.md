[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 设置鼠标指针，光标等待效�?
```aardio aardio
//设置鼠标指针
import win.ui;
/*DSG{{*/
var winform = win.form(text="设置鼠标指针，光标等待效�?;right=349;bottom=249)
winform.add(
button={cls="button";text="光标等待";left=110;top=114;right=229;bottom=155;z=2};
static={cls="static";text="www.aardio.com";left=93;top=41;right=266;bottom=72;align="center";color=16711680;edge=1;font=LOGFONT(name='Microsoft Sans Serif';underline=1);notify=1;transparent=1;z=1}
)
/*}}*/

winform.button.oncommand = function(id,event){
    winform.button.text = "请稍�?....."
    winform.button.disabled = true;

    win.ui.waitCursor(true);//鼠标指针进入等待状�?    win.delay(2000)
    win.ui.waitCursor(false);;//还原鼠标指针

    winform.button.text = "已完�?
    winform.button.disabled = false;
}

import win.cur;

//鼠标回到窗体上时,切换鼠标为箭�?winform.wndproc = function(hwnd,message,wParam,lParam){
    if(message =  0x20/*_WM_SETCURSOR*/){
        win.cur.load(0x7F00/*_IDC_ARROW*/)
        win.cur.setCur();
    }
}

//当鼠标指针移到静态控件上�?切换鼠标为手�?var hand = win.cur.load(32649/*_IDC_HAND*/)
winform.static.wndproc = function(hwnd,message,wParam,lParam){
    if(message = 0x200/*_WM_MOUSEMOVE*/) {
        win.cur.setCur(hand);
    }
}

winform.show(true);
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Effects/cur.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Effects/cur.md')

