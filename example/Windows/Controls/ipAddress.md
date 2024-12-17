[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: IP鍦板潃鎺т欢婕旂ず

```aardio aardio
//IP鍦板潃鎺т欢
import win.ui;
/*DSG{{*/
var winform = win.form(text="IP鍦板潃鎺т欢婕旂ず";right=599;bottom=399)
winform.add(
ipAddress={cls="ipaddress";text="IP 鍦板潃";left=152;top=84;right=408;bottom=105;bgcolor=16777215;edge=1;z=1}
)
/*}}*/

winform.ipAddress.setRange("10.1.0.0","10.10.255.255");
winform.ipAddress.address = 10 << 24 | 1 << 16;

winform.ipAddress.onFieldChanged = function(field,value){
    winform.text = winform.ipAddress.text + " 鍙樻洿浣嶇疆:" + field + " 鏁板�?" + value;
}

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Controls/ipAddress.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Controls/ipAddress.md')

