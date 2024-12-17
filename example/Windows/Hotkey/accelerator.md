[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?CTRL + N �?ALT + C

```aardio aardio
//窗口快捷�?import win.ui;
/*DSG{{*/
var winform = win.form(text="�?CTRL + N �?ALT + C";right=759;bottom=469)
/*}}*/

import win.ui.accelerator;
var accelerator = win.ui.accelerator({

    {
        ctrl = true; vkey = 'N'#;
        oncommand = function() winform.msgbox("CTRL+N");
    };

    {
        alt = true; vkey = 'C'#;
        oncommand = function() winform.msgbox("ALT+C");
    };

},winform );

/*
win.ui.accelerator创建的快捷键限于指定窗口内生效�?
var accelerator = win.ui.accelerator( accTable,winform )
上述代码创建快捷键时有两个参数，accTable应该是一个指定快捷键的数组�?
每一个快揵键使用以下字段指定快捷键的属�?

ctrl 如果为true按ctrl键生�?alt 如果为true按alt键生�?shift 如果为true按shift键生�?vkey 指定虚拟键码，虚拟键码参考标准库里的 key.VK ，可使用_VK前缀的常量指定，普通字符用大写的字节码指定
cmd 指定快捷键触发的命令ID，如果指定了oncommand可以省略cmd字段
oncommand 指定一个响应快捷键的事件，win.ui.accelerator会自动调�?winform.registCommand()生成cmd的�?
win.ui.accelerator在绑定窗体时�?会添�?winform.preTranslateAccelerator() 事件用于拦截快捷键消息并响应事件�?*/

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Hotkey/accelerator.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Hotkey/accelerator.md')

