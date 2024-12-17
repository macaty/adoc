[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 系统任务栏显示进�? 调用ITaskbarList3接口 )

```aardio aardio
//窗口程序 - 在系统任务栏显示进度
import win.ui;
/*DSG{{*/
var winform = win.form(text="系统任务栏显示进�? 调用ITaskbarList3接口 )";right=599;bottom=399)
winform.add(
button={cls="button";text="显示任务栏进�?;left=219;top=240;right=459;bottom=327;z=1}
)
/*}}*/

import com.interface.ITaskbarList3;
winform.wndproc = function(hwnd,message,wParam,lParam){
    select( message ) {
        case _WM_TASKBARBUTTONCREATED{
            winform.taskbar = com.interface.ITaskbarList3.Create()
        }
    }
}

winform.button.oncommand = function(id,event){
    if(!winform.taskbar) return; //XP下该值为空所有会忽略下面的代�?
    for(i=1;10;1){
        winform.taskbar.SetProgressValue(winform.hwnd,i,10)
        win.delay(1000)
    }
}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Effects/ITaskbarList3.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Effects/ITaskbarList3.md')

