[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 娉ㄥ唽琛ㄥ揩閫熷畾浣?www.aardio.com

```aardio aardio
//娉ㄥ唽琛ㄦ搷浣?- 蹇�熷畾浣?import win.ui;
/*DSG{{*/
var winform = win.form(text="娉ㄥ唽琛ㄥ揩閫熷畾浣?www.aardio.com";right=512;bottom=131;)
winform.add(
button={cls="button";text="蹇�熷畾浣?;left=296;top=68;right=440;bottom=101;z=2};
edit={cls="edit";text="HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\Main\FeatureControl\FEATURE_TABBED_BROWSING";left=39;top=32;right=482;bottom=61;edge=1;z=1}
)
/*}}*/

import win.reg;
import process;
import win.clip

var str  = win.clip.read();
if( str ? string.startWith(str,"HKEY_") ){
    winform.edit.text = str;
}

winform.button.oncommand = function(id,event){
    var reg = win.reg("HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Applets\Regedit")
    reg.setSzValue("LastKey",winform.edit.text)
    process.execute("regedit.exe")
}

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Registry/lastkey.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Registry/lastkey.md')

