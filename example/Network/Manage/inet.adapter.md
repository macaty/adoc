[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 网络连接

```aardio aardio
//网络连接
import console.int;

import inet.mac;
console.log("当前联网MAC",inet.mac.getAddress("www.aardio.com") )

import inet.adapterInfo;
for adapterInfo in inet.adapterInfo.each(2/*_AF_INET*/) {
    console.log(adapterInfo.netConnectionId)
    console.log(adapterInfo.description)
    console.log("网卡是否可用",adapterInfo.operStatusUp)
    console.log("是否无线网卡",adapterInfo.ifTypeWireless)

    for addr,strAddr in adapterInfo.eachUnicastAddress(){
        console.log(strAddr)
    }

    if(adapterInfo.operStatusUp){
        console.log("网卡已连�?);
    }
    else {
        console.log("网卡未连�?);
    }

    console.more(1)
}

return;

import inet.adapter;
for adptInfo in ..inet.adapter.each() {

    console.log(adptInfo.mac); //MAC 地址
    console.log(adptInfo.adapterName); //GUID
    console.log(adptInfo.description); //网卡描述
    console.log(adptInfo.netConnectionId); //网络连接 ID
    console.log(adptInfo.pnpInstanceId); //设备实例ID
    console.log(adptInfo.index); //索引
    console.log(adptInfo.type,"type "); //索引

    if(adptInfo.type==71/*_IF_TYPE_IEEE80211*/){
        console.log("无线网卡")
    }

    //获取所�?IP
    for( addr,strAddr in adptInfo.eachAddress() ){
        console.log(strAddr);
    }

    if(adptInfo.pnpInstanceId){
        //import process.devcon;

        //启用网卡，进程需要以管理权限启动
        //process.devcon.enable("@"+adptInfo.pnpInstanceId))

        //禁用网址，进程需要以管理权限启动
        //process.devcon.disable("@"+adptInfo.pnpInstanceId))
    }

    console.more(1)
}

console.pause();

/*
//调用 WMI 获取网络连接，注�?NetConnectionID 是连接名
import com.wmi;
for item in com.wmi.eachProperties("Win32_NetworkAdapter") {
    console.dump(item)
}
*/

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/Manage/inet.adapter.md)

