[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口程序 - 毛玻璃效�?
```aardio aardio
//窗口程序 - 毛玻璃效�?import win.ui;
/*DSG{{*/
var winform = win.form(text="毛玻璃效�?;right=759;bottom=469)
winform.add()
/*}}*/

::DwmApi := raw.loadDll("Dwmapi.dll")
var aero = function(hwnd){
    if(_WIN10_LATER){
        var accent = {
            int AccentState = 3;
            INT AccentFlags = 0;
            INT GradientColor = 0;
            INT AnimationId = 0;
        };

        ::User32.SetWindowCompositionAttribute(hwnd,{
            INT Attrib = 19;
            ptr pvData = raw.buffer(accent);
            INT cbData = raw.sizeof(accent);
        });
    }
    elseif(_WIN7_LATER) {
        var result = {bool enabled};
        ::DwmApi.DwmIsCompositionEnabled(result)
        if(result.enabled){
            ::DwmApi.DwmEnableBlurBehindWindow(hwnd,{ int flags=3;int enable=1;int rgnBlur;int transition})
        }
    }
}
aero( winform.hwnd );

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Effects/aero.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Effects/aero.md')

