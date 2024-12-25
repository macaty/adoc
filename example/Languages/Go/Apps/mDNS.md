[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Go 语言 - mDNS 发现设备

```aardio aardio
//aardio 调用 Go 语言 - mDNS 发现设备
/*
请参考：范例 > 网络应用 > wsock > udp > SSDP 发现设备�?以及 process.adb 扩展库范例�?*/
import console.int;
import golang.mdns;//DLL 源码：\lib\golang\mdns\.go\build.aardio

console.showLoading(" 扫描")
//------------------------------------------
var serviceInfos = golang.mdns.scan()
console.dumpJson(serviceInfos)

console.showLoading(" 查询")
//------------------------------------------
var serviceInfos = golang.mdns.query(
    service="_test._udp";
    domain = "local";
    timeout = 3000;
)
console.dumpJson(serviceInfos)

console.showLoading(" 简单查�?)
//------------------------------------------
var serviceInfos = golang.mdns.lookup("_test._udp")
console.dumpJson(serviceInfos)

//发布 mDNS 服务，注意本机查询不到本机服�?golang.mdns.startService(
    instance = "name";
    service = "_httpabcdefg._tcp";
    port = 8888;
    txt = {"文本"}
)

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Go/Apps/mDNS.md)

