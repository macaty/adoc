[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 临视窗口创建销�?
```aardio aardio
//临视窗口创建销�?import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=448;bottom=249;)
winform.add(
edit={cls="edit";left=8;top=13;right=437;bottom=239;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

import win.util.shellhook;
var shellhook = win.util.shellhook(winform);

shellhook.onShellHook=function(hshell,hwnd){

    //获取线程ID,进程ID
    var tid,pid = win.getThreadProcessId(hwnd);
    if(tid== thread.getId()){
        /*return 如果不想临视本线程在这里退�?/
    }

    //判断钩子拦截到的消息类型
    select(hshell ) {
        case 0x1/*_HSHELL_WINDOWCREATED*/ {
            winform.edit.text +=   "一个窗口创�?+hwnd+"进程ID�? + pid + "线程ID:" +tid + '\r\n    标题:' + win.getText(hwnd) + '\r\n\r\n'
        }
        case 0x2/*_HSHELL_WINDOWDESTROYED*/{
            winform.edit.text += "一个窗口销�?+hwnd+"进程ID�? + pid + "线程ID:" +tid  + '\r\n   标题:' + win.getText(hwnd) + '\r\n\r\n'
        }
        case 0x4/*_HSHELL_WINDOWACTIVATED*/{
            winform.edit.text += "一个窗口激�?+hwnd+"进程ID�? + pid + "线程ID:" +tid  + '\r\n   标题:' + win.getText(hwnd) + '\r\n\r\n'
        }

     }
}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Automation/Windows/shellhook.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Automation/Windows/shellhook.md')

