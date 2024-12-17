[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 澶氭闈?
```aardio aardio
//澶氭闈?import win.ui;
import win.util.desktop;
/*DSG{{*/
var winform = win.form(text="aardio form";right=262;bottom=179;)
winform.add(
btnDefault={cls="button";text="鍒囨崲鍒伴粯璁ゆ闈?;left=53;top=110;right=202;bottom=143;font=LOGFONT(name='Microsoft Sans Serif');z=3};
btnToMyDesktop={cls="button";text="鍒囨崲鍒癿yDesktop";left=53;top=64;right=202;bottom=97;font=LOGFONT(name='Microsoft Sans Serif');z=2};
static={cls="static";text="ctrl + D 璇曡瘯";left=59;top=27;right=229;bottom=62;color=255;font=LOGFONT(h=-21;name='瀹嬩綋');transparent=1;z=1}
)
/*}}*/

var virDesktp = win.util.desktop();
virDesktp.create("myDesktop") //鍒涘缓妗岄潰

hkid = winform.reghotkey(function(id,mod,vk){
    virDesktp.switch( ) //鍒囨崲妗岄潰
},2/*_MOD_CONTROL*/,'D'#);

winform.btnDefault.oncommand = function(id,event){
    virDesktp.switch("Default" )
}

winform.btnToMyDesktop.oncommand = function(id,event){
    virDesktp.switch("myDesktop" ) //鍒囨崲妗岄潰
}

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Desktop/MultiDesktop.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Desktop/MultiDesktop.md')

