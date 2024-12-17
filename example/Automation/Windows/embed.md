[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口自动�?- 嵌入外部窗口

```aardio aardio
//窗口自动�?- 嵌入外部窗口
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=886;bottom=627;)
winform.add(
button={cls="button";text="点这里试�?;left=554;top=561;right=801;bottom=620;color=14120960;db=1;dr=1;font=LOGFONT(h=-14);note="这点里操作记事本的编辑框";z=2};
static={cls="static";left=46;top=22;right=854;bottom=542;db=1;dl=1;dr=1;dt=1;z=1}
)
/*}}*/

import process;
if( !process.executeWaitInput("wordpad.exe") ){
    error("系统未安装写字板");
}

import winex;
var hwndNotepad,hNotepadEdit = winex.waitActive(,,"WordPadClass","RICHEDIT50W");

//悬浮影子窗口：外部进程窗口附加到 winform.static 并如影随形的自适应缩放调整位置
winex.orphanWindow(winform.static,hwndNotepad)

//退出程序前让记事本退�?winform.onClose = function(hwnd,message,wParam,lParam){
   if(!winex.closeAndWait(hwndNotepad)) return 1;
}

import winex.ctrl.edit;
var edit = winex.ctrl.edit(hNotepadEdit);
winform.button.oncommand = function(id,event){
    edit.text="测试一�?;
    edit.print("测试调用函数",123,{
        1,2,3
    })
}

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Automation/Windows/embed.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Automation/Windows/embed.md')

