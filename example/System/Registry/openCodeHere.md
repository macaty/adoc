[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 娉ㄥ唽琛ㄦ搷浣?- 鍙抽敭鑿滃崟娣诲姞鎵撳紑 VSCode

```aardio aardio
//娉ㄥ唽琛ㄦ搷浣?- 鍙抽敭鑿滃崟娣诲姞鎵撳紑 VSCode
import win;
import win.reg;
import process.code;

var codePath = process.code.path;
if(!codePath){
    win.msgboxErr("鏈畨瑁?Visual Studio Code");
    return;
}

var reg = win.reg("HKEY_CURRENT_USER\Software\Classes\*\shell\VSCode")
reg.setSzValue("","Open with Code")
reg.setSzValue("Icon",codePath+",0")

var reg = win.reg("HKEY_CURRENT_USER\Software\Classes\*\shell\VSCode\command")
reg.setSzValue("",`"`+codePath+`" "%1"`)

var reg = win.reg("HKEY_CURRENT_USER\Software\Classes\Directory\shell\VSCode")
reg.setSzValue("","Open with Code")
reg.setSzValue("Icon",codePath+",0")

var reg = win.reg("HKEY_CURRENT_USER\Software\Classes\Directory\shell\VSCode\command")
reg.setSzValue("",`"`+codePath+`" "%V"`)

var reg = win.reg("HKEY_CURRENT_USER\Software\Classes\Directory\Background\shell\VSCode")
reg.setSzValue("","Open with Code")
reg.setSzValue("Icon",codePath+",0")

var reg = win.reg("HKEY_CURRENT_USER\Software\Classes\Directory\Background\shell\VSCode\command")
reg.setSzValue("",`"`+codePath+`" "%v."`)

win.msgbox("宸叉坊鍔犺彍鍗?)

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Registry/openCodeHere.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Registry/openCodeHere.md')

