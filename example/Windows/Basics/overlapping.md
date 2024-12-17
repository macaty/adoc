[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 控件重叠 - 请拖动窗口改变大小试�?
```aardio aardio
//窗口程序 - 控件重叠
//Z序原理与优化: https://www.aardio.com/zh-cn/doc/library-guide/std/win/ui/z-order.html
import win.ui;
/*DSG{{*/
var winform = win.form(text="控件重叠 - 请拖动窗口改变大小试�?;right=584;bottom=509)
winform.add(
bk={cls="bk";text="这是 bk 背景贴图控件，可以随意重�?;left=19;top=313;right=557;bottom=484;bgcolor=32768;color=16777215;db=1;dl=1;dr=1;valign="bottom";z=2};
bk2={cls="bk";left=19;top=472;right=557;bottom=491;bgcolor=32768;db=1;dl=1;dr=1;z=1};
btnChild={cls="button";text="此控件不会被 edit 控件挡住或者干�?;left=202;top=377;right=524;bottom=448;db=1;dr=1;z=6};
btnClipSiblings={cls="button";text="此控件在后面，但反而穿透显示在前面�?;left=244;top=179;right=566;bottom=250;db=1;dr=1;z=4};
editClipSiblings={cls="edit";text="�?edit 控件【重叠裁剪】属性为 true";left=19;top=146;right=521;bottom=261;clip=1;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;z=5};
editParent={cls="edit";text="�?edit 控件已设为下�?button 控件的父窗口";left=37;top=323;right=539;bottom=458;db=1;dl=1;dr=1;edge=1;multiline=1;z=3};
lbClipSiblings={cls="static";text='动态控件默认是不能前后重叠的。\r\n只有 bk,bkplus 这种无窗口背景贴图控件可以任意重叠。\r\n或�?static,plus 设为静态模式（不响应事件回调，notify 属性为false）可以重叠。\r\n\r\n有两种方法让动态控件可以前后叠放。\r\n\r\n1、把被遮挡的控件放在后面，前面的控件设置『重叠裁剪』为 true。\r\n这时候前面的控件就会挖个洞不再挡住后面的控件，显示顺序会反过来�?;left=19;top=12;right=513;bottom=141;dl=1;dr=1;dt=1;transparent=1;z=7};
lbSetParent={cls="static";text='2、前面的控件设置背景控件为父窗口，例如：\r\nwinform.btnChild.setParent( winform.editParent );';left=19;top=274;right=513;bottom=317;db=1;dl=1;dr=1;transparent=1;z=8}
)
/*}}*/

//设置父窗�?winform.btnChild.setParent( winform.editParent );

//分发子窗口命令消�?winform.editParent.translateCommand()

/*
响应命令�?_WM_COMMAND 是由控件发送给父窗口，
父窗口解析此消息才能调用控件�?oncommand 函数�?父窗口必须调�?translateCommand() 函数�?*/
winform.btnChild.oncommand = function(id,event){
    winform.msgbox("测试","控件重叠测试");
}

import win.ui.minmax;
win.ui.minmax(winform);

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Basics/overlapping.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Basics/overlapping.md')

