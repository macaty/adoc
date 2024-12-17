[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 系统热键

```aardio aardio
//系统热键
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=469;)
winform.add(
button={cls="button";text="设置为系统热�?;left=281;top=32;right=517;bottom=63;z=2};
hotkey={cls="hotkey";left=49;top=35;right=268;bottom=55;edge=1;z=1};
static={cls="static";left=47;top=107;right=679;bottom=424;transparent=1;z=3}
)
/*}}*/

var hkId;
winform.button.oncommand = function(id,event){

    //删除之前注册的热�?hkId如果是null空值，此函数可忽略不做任何�?    winform.unreghotkey(hkId);

    //重新注册系统热键;
    hkId = winform.reghotkey(

        function(id,mod,vk){
            winform.msgbox("你按了刚才设置的那个啥！")
        }

        //winform.hotkey.gethotkey()刚好返回2个值对应最后两个参�?        ,winform.hotkey.gethotkey()
    );

/**
    winform.reghotkey(回调函数,控制�?虚拟键码)

    此函数共有三个参�?一般直接写参数的方法如下，参数说明�?    mod为控制键,使用_MOD_前缀的常量表�?0为不按下控制�?
    vk为虚拟键�?使用_VK_前缀的常量表示，对于普通字符按键可以使用大写形式的字节码表示�?
    示例:
    hkid = winform.reghotkey(function(id,mod,vk){

    },0x2/*_MOD_CONTROL*/,'D'#);

    �?winform.hotkey.gethotkey() 函数刚好可以返回2个�?控制�?虚拟键码)�?    而这2个返回值，刚好可以作为调用 winform.reghotkey 函数的最后两个参数�?**/

}

winform.static.text = "系统热键全局有效，即使切换到桌面上的其他程序窗口，热键仍然有�?

winform.enableDpiScaling();
winform.show();

win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Hotkey/hotkey.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Hotkey/hotkey.md')

