[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 娉ㄥ唽琛ㄦ搷浣?- 娓呴櫎杩滅▼妗岄潰杩炴帴璁板綍

```aardio aardio
//娉ㄥ唽琛ㄦ搷浣?- 娓呴櫎杩滅▼妗岄潰杩炴帴璁板綍
import win.reg;

var reg = win.reg("HKEY_CURRENT_USER\SOFTWARE\Microsoft\Terminal Server Client\Default")
for(name,value,t in reg.eachValue()) {
    if(string.startWith(name,"MRU")){
        reg.delValue(name)
    }
}

var reg = win.reg("HKEY_CURRENT_USER\SOFTWARE\Microsoft\Terminal Server Client\Servers")
for(keyName,writeTime in reg.eachKey() ){
    reg.delKey(keyName)
}

io.remove(io.getSpecial(0x5/*_CSIDL_MYDOCUMENTS*/,"Default.rdp"))

import win.dlg.message;
win.dlg.message().ok("宸叉竻闄よ繙绋嬫闈㈣繛鎺ヨ褰?)

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Registry/rdp.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Registry/rdp.md')

