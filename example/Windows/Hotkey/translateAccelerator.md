[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鑷畾涔夊揩鎹烽敭

```aardio aardio
//鑷畾涔夊揩鎹烽敭
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=469;)
winform.add(
edit={cls="edit";text="鍦ㄦ枃鏈閲岄潰锛屾寜 CTRL + A 璇曡瘯";left=88;top=64;right=664;bottom=368;edge=1;multiline=1;z=1}
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Hotkey/translateAccelerator.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Hotkey/translateAccelerator.md')

