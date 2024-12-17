[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 缃戝崱璁惧

```aardio aardio
//缃戝崱璁惧
import console;
import sys.networkCards;
import inet.adapterInfo;

//鍒楀嚭鎵�鏈夌綉鍗¤澶?for networkCard in sys.networkCards.each(){
    console.log(networkCard.netConnectionId)
    console.log(networkCard.description)
    console.log(networkCard.pnpInstanceId)

    var adapterInfo = inet.adapterInfo.get(networkCard.adapterName);
    if(adapterInfo){
        console.log(adapterInfo.mac); //MAC 鍦板潃
        console.log(adapterInfo.adapterName); //GUID
        console.log(adapterInfo.description); //缃戝崱鎻忚堪
        console.log("缃戝崱宸插惎鐢?);

        if(adapterInfo.operStatusUp){
            console.log("缃戝崱宸茶繛鎺?);
        }
        else {
            console.log("缃戝崱鏈繛鎺?);
        }

    }
    else {
        console.log("缃戝崱宸茬鐢?);
    }

    console.more()
}

console.pause(true);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/Manage/sys.networkCards.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/Manage/sys.networkCards.md')

