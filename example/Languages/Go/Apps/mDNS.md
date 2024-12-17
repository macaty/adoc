[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 Go 璇█ - mDNS 鍙戠幇璁惧

```aardio aardio
//aardio 璋冪敤 Go 璇█ - mDNS 鍙戠幇璁惧
/*
璇峰弬鑰冿細鑼冧緥 > 缃戠粶搴旂敤 > wsock > udp > SSDP 鍙戠幇璁惧锛?浠ュ強 process.adb 鎵╁睍搴撹寖渚嬨�?*/
import console.int;
import golang.mdns;//DLL 婧愮爜锛歕lib\golang\mdns\.go\build.aardio

console.showLoading(" 鎵弿")
//------------------------------------------
var serviceInfos = golang.mdns.scan()
console.dumpJson(serviceInfos)

console.showLoading(" 鏌ヨ")
//------------------------------------------
var serviceInfos = golang.mdns.query(
    service="_test._udp";
    domain = "local";
    timeout = 3000;
)
console.dumpJson(serviceInfos)

console.showLoading(" 绠�鍗曟煡璇?)
//------------------------------------------
var serviceInfos = golang.mdns.lookup("_test._udp")
console.dumpJson(serviceInfos)

//鍙戝竷 mDNS 鏈嶅姟锛屾敞鎰忔湰鏈烘煡璇笉鍒版湰鏈烘湇鍔?golang.mdns.startService(
    instance = "name";
    service = "_httpabcdefg._tcp";
    port = 8888;
    txt = {"鏂囨湰"}
)

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Go/Apps/mDNS.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Go/Apps/mDNS.md')

