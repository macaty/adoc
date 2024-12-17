[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 绐楀彛绋嬪簭 - 姣涚幓鐠冩晥鏋?
```aardio aardio
//绐楀彛绋嬪簭 - 姣涚幓鐠冩晥鏋?import win.ui;
/*DSG{{*/
var winform = win.form(text="姣涚幓鐠冩晥鏋?;right=759;bottom=469)
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Effects/aero.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Effects/aero.md')

