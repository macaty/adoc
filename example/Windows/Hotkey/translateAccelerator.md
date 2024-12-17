[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 自定义快捷键

```aardio aardio
//自定义快捷键
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=469;)
winform.add(
edit={cls="edit";text="在文本框里面，按 CTRL + A 试试";left=88;top=64;right=664;bottom=368;edge=1;multiline=1;z=1}
)
/*}}*/

winform.edit.translateAccelerator = function( msg ){

    var ctrl = ::GetKeyState(0x11/*_VK_CTRL*/) & 0x8000;
    var shift =  ::GetKeyState(0x10/*_VK_SHIFT*/) & 0x8000;
    var alt = ::GetKeyState(0x12/*_VK_ALT*/) & 0x8000;

    var vk = msg.wParam;
    if(  ( vk == 'A'# ) && ctrl  ){
        if(msg.message == 0x100/*_WM_KEYDOWN*/){
            winform.edit.selectAll();
            return true;
        }
    }
}

winform.enableDpiScaling();
winform.show();

win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Hotkey/translateAccelerator.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Hotkey/translateAccelerator.md')

