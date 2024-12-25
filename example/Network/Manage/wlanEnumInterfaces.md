[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: RUNAS//无线连接

```aardio aardio
//RUNAS//无线连接
//相关范例: ~\codes\范例程序\G) 操作系统\6) 事件日志\2.EventLogReader.aardio
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

//创建命令行进程（显示 WIFI 连接名）
var prcsWifi = process.popen("netsh wlan show profiles");

//遍历进程所有输出项，参数指定模式匹配表达式
for wifi in prcsWifi.lines("<All User Profile>|<所有用户配置文�?\s*\:\s*(.*)"){

    //创建命令行进程（显示密码�?    var prcsKey = process.popen("netsh wlan show profile name="+wifi+" key=clear");

    for password in prcsKey.lines("<Key Content>|<关键内容>\s*\:\s*(.*)"){
        console.log( wifi, password );
    }
}
*/

console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/Manage/wlanEnumInterfaces.md)

