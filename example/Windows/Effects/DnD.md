[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口程序 - 文件拖放

```aardio aardio
//窗口程序 - 文件拖放
import win.ui;
/*DSG{{*/
var winform = win.form(text="窗口程序 - 文件拖放";right=759;bottom=469)
winform.add(
edit={cls="edit";left=69;top=34;right=693;bottom=377;autohscroll=false;edge=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

/*
拖放会触�?onDropFiles 事件�?定义此事件会自动执行 ::Shell32.DragAcceptFiles(winform.hwnd,true) 以启用拖放支持�?
要特别注意有管理权限的窗口不能接受拖放，新系统已经完全禁止了这种操作�?*/
winform.onDropFiles = function(files){
    winform.edit.print(files)
}

winform.text = "请拖放一个或多个文件到窗口上"

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Effects/DnD.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Effects/DnD.md')
