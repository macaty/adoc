[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 网卡设备

```aardio aardio
//网卡设备
import console;
import sys.networkCards;
import inet.adapterInfo;

//列出所有网卡设�?for networkCard in sys.networkCards.each(){
    console.log(networkCard.netConnectionId)
    console.log(networkCard.description)
    console.log(networkCard.pnpInstanceId)

    var adapterInfo = inet.adapterInfo.get(networkCard.adapterName);
    if(adapterInfo){
        console.log(adapterInfo.mac); //MAC 地址
        console.log(adapterInfo.adapterName); //GUID
        console.log(adapterInfo.description); //网卡描述
        console.log("网卡已启�?);

        if(adapterInfo.operStatusUp){
            console.log("网卡已连�?);
        }
        else {
            console.log("网卡未连�?);
        }

    }
    else {
        console.log("网卡已禁�?);
    }

    console.more()
}

console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/Manage/sys.networkCards.md)

