[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 娉ㄥ唽琛ㄦ搷浣?- 鍙抽敭鑿滃崟娣诲姞鎵撳紑鍛戒护琛?
```aardio aardio
//娉ㄥ唽琛ㄦ搷浣?- 鍙抽敭鑿滃崟娣诲姞鎵撳紑鍛戒护琛?import win;
import win.reg;
import win.version;

/*
鍙嬫儏鎻愰啋锛氬湪璧勬簮绠＄悊鍣ㄧ殑鍦板潃鏍忕洿鎺ヨ緭鍏?cmd"鍚庡洖杞︼紝涔熷彲浠ュ湪褰撳墠鐩綍鎵撳紑鍛戒护琛?*/
if(win.version.isWin10Later){
    var reg = win.reg("HKEY_CURRENT_USER\Software\Classes\Directory\Background\shell\OpenCmdHere")
    reg.setSzValue("","鍦ㄦ澶勬墦寮�鍛戒护琛岀獥鍙?)
    reg.setSzValue("Extended","") //鍦ㄨ祫婧愮鐞嗗櫒鎸塖hift骞舵寜鍙抽敭鎵嶅嚭鏉?
    var reg = win.reg("HKEY_CURRENT_USER\Software\Classes\Directory\Background\shell\OpenCmdHere\command")
    reg.setSzValue("","cmd.exe -noexit -command Set-Location -literalPath '%V'")
}

var reg = win.reg("HKEY_CURRENT_USER\Software\Classes\Directory\Background\shell\runas")
reg.setSzValue("","鍦ㄦ澶勬墦寮�鍛戒护琛岀獥鍙?绠＄悊鍛?")
reg.setSzValue("HasLUAShield","")  //鏄剧ず鐩剧墝鍥炬爣
reg.setSzValue("Extended","")  //鍦ㄨ祫婧愮鐞嗗櫒鎸塖hift骞舵寜鍙抽敭鎵嶅嚭鏉?
var reg = win.reg("HKEY_CURRENT_USER\Software\Classes\Directory\Background\shell\runas\command")
reg.setSzValue("",'cmd.exe /s /k pushd \"%V\"');

win.msgbox("宸叉坊鍔犺彍鍗?)

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Registry/openCmdHere.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Registry/openCmdHere.md')

