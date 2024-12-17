[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 娉ㄥ唽琛ㄦ搷浣?- Win11 鍙抽敭鑿滃崟椋庢牸鍒囨崲

```aardio aardio
//RUNAS//娉ㄥ唽琛ㄦ搷浣?- Win11 鍙抽敭鑿滃崟椋庢牸鍒囨崲
import win.ui;
/*DSG{{*/
var winform = win.form(text="Windows 11 鍙抽敭鑿滃崟鍒囨崲宸ュ叿";right=389;bottom=166;border="dialog frame";max=false)
winform.add(
radioWin10={cls="radiobutton";text="Win10 椋庢牸缁忓吀鍙抽敭鑿滃崟";left=44;top=46;right=217;bottom=86;z=1};
radioWin11={cls="radiobutton";text="Win11 椋庢牸鍙抽敭鑿滃崟";left=44;top=84;right=233;bottom=127;z=2}
)
/*}}*/

import win.reg;
import win.version;
import process;
winform.radioWin10.oncommand = function(id,event){
    var reg = win.regWow64( "HKEY_CURRENT_USER\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}")
    reg.setSzValue("","")

    var reg = win.regWow64( "HKEY_CURRENT_USER\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32")
    reg.setSzValue("","")
    reg.close();

    ::Shell32.SHChangeNotify(0x8000000/*_SHCNE_ASSOCCHANGED*/,0,0,0);
     process.kill("explorer.exe",true)
}

winform.radioWin11.oncommand = function(id,event){
    var reg = win.regWow64("HKEY_CURRENT_USER\Software\Classes\CLSID")
    reg.delKeyTree("{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}")
    reg.close();

    ::Shell32.SHChangeNotify(0x8000000/*_SHCNE_ASSOCCHANGED*/,0,0,0);
    process.kill("explorer.exe",true)
}

if(!win.version.isWin11Later){
    win.msgboxErr("姝ゅ伐鍏蜂粎鐢ㄤ簬 Windows 11");
    return;
}

var reg = win.regWow64("HKEY_CURRENT_USER\Software\Classes\CLSID")
winform.radioWin10.checked = reg.open("{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}",true);
winform.radioWin11.checked = !winform.radioWin10.checked;
reg.close();

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Registry/win11Menu.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Registry/win11Menu.md')

