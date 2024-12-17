[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.util.shellhook 库模块帮助文�?
## win.util 成员列表

### win.util.shellhook()

[返回对象:winUtilShellhookObject](#winUtilShellhookObject)

### win.util.shellhook(输入winform对象)

创建一个通知窗口

在所有窗口创建销毁时接收消息

## winUtilShellhookObject 成员列表

### winUtilShellhookObject.onShellHook

```aardio aardio
winUtilShellhookObject.onShellHook=function(hShell,hwnd){
    var tid,pid = win.getThreadProcessId(hwnd)
    if(tid!= thread.getId()){
        return; /*如果不想临视本线程在这里退�?/
    }
    select(hShell) {
        case 1/*_HSHELL_WINDOWCREATED*/ {
            ..io.print("一个窗口创�?,hwnd,"进程ID�? + pid + "线程ID:" +tid)
        }
        case 2/*_HSHELL_WINDOWDESTROYED*/{
            ..io.print("一个窗口销�?,hwnd,"进程ID�? + pid + "线程ID:" +tid)
        }
     }
}

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/util/shellhook.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/util/shellhook.md')

