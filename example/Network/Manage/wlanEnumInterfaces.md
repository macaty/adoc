[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: RUNAS//鏃犵嚎杩炴帴

```aardio aardio
//RUNAS//鏃犵嚎杩炴帴
//鐩稿叧鑼冧緥: ~\codes\鑼冧緥绋嬪簭\G) 鎿嶄綔绯荤粺\6) 浜嬩欢鏃ュ織\2.EventLogReader.aardio
import console;
import sys.wlan;
import crypt.protectData;
import thread.token;

thread.token.impersonate("winlogon.exe",function(){

    var wlan = sys.wlan();
    for name,guid,description,flags,access,xmlProfile in wlan.eachProfile(){

        var km = xmlProfile.queryEle(
            tagName = "keyMaterial"
        );

        var password = crypt.protectData.decrypt(km.innerText())
        console.log(name,password,description)
    }
})

/*
import process.popen;

//鍒涘缓鍛戒护琛岃繘绋嬶紙鏄剧ず WIFI 杩炴帴鍚嶏級
var prcsWifi = process.popen("netsh wlan show profiles");

//閬嶅巻杩涚▼鎵�鏈夎緭鍑洪」锛屽弬鏁版寚瀹氭ā寮忓尮閰嶈〃杈惧紡
for wifi in prcsWifi.lines("<All User Profile>|<鎵�鏈夌敤鎴烽厤缃枃浠?\s*\:\s*(.*)"){

    //鍒涘缓鍛戒护琛岃繘绋嬶紙鏄剧ず瀵嗙爜锛?    var prcsKey = process.popen("netsh wlan show profile name="+wifi+" key=clear");

    for password in prcsKey.lines("<Key Content>|<鍏抽敭鍐呭>\s*\:\s*(.*)"){
        console.log( wifi, password );
    }
}
*/

console.pause(true);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/Manage/wlanEnumInterfaces.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/Manage/wlanEnumInterfaces.md')

