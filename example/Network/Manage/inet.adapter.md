[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 缃戠粶杩炴帴

```aardio aardio
//缃戠粶杩炴帴
import console.int;

import inet.mac;
console.log("褰撳墠鑱旂綉MAC",inet.mac.getAddress("www.aardio.com") )

import inet.adapterInfo;
for adapterInfo in inet.adapterInfo.each(2/*_AF_INET*/) {
    console.log(adapterInfo.netConnectionId)
    console.log(adapterInfo.description)
    console.log("缃戝崱鏄惁鍙敤",adapterInfo.operStatusUp)
    console.log("鏄惁鏃犵嚎缃戝崱",adapterInfo.ifTypeWireless)

    for addr,strAddr in adapterInfo.eachUnicastAddress(){
        console.log(strAddr)
    }

    if(adapterInfo.operStatusUp){
        console.log("缃戝崱宸茶繛鎺?);
    }
    else {
        console.log("缃戝崱鏈繛鎺?);
    }

    console.more(1)
}

return;

import inet.adapter;
for adptInfo in ..inet.adapter.each() {

    console.log(adptInfo.mac); //MAC 鍦板潃
    console.log(adptInfo.adapterName); //GUID
    console.log(adptInfo.description); //缃戝崱鎻忚堪
    console.log(adptInfo.netConnectionId); //缃戠粶杩炴帴 ID
    console.log(adptInfo.pnpInstanceId); //璁惧瀹炰緥ID
    console.log(adptInfo.index); //绱㈠紩
    console.log(adptInfo.type,"type "); //绱㈠紩

    if(adptInfo.type==71/*_IF_TYPE_IEEE80211*/){
        console.log("鏃犵嚎缃戝崱")
    }

    //鑾峰彇鎵�鏈?IP
    for( addr,strAddr in adptInfo.eachAddress() ){
        console.log(strAddr);
    }

    if(adptInfo.pnpInstanceId){
        //import process.devcon;

        //鍚敤缃戝崱锛岃繘绋嬮渶瑕佷互绠＄悊鏉冮檺鍚姩
        //process.devcon.enable("@"+adptInfo.pnpInstanceId))

        //绂佺敤缃戝潃锛岃繘绋嬮渶瑕佷互绠＄悊鏉冮檺鍚姩
        //process.devcon.disable("@"+adptInfo.pnpInstanceId))
    }

    console.more(1)
}

console.pause();

/*
//璋冪敤 WMI 鑾峰彇缃戠粶杩炴帴锛屾敞鎰?NetConnectionID 鏄繛鎺ュ悕
import com.wmi;
for item in com.wmi.eachProperties("Win32_NetworkAdapter") {
    console.dump(item)
}
*/

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/Manage/inet.adapter.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/Manage/inet.adapter.md')

