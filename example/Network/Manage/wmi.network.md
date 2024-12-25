[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: RUNAS//启用禁用网卡

```aardio aardio
//RUNAS//启用禁用网卡
import process
import console;
if(_WINXP) return console.logPause("本程序不支持 XP 系统");

/*
也可以使用扩展库 process.devcon 启用禁用网卡驱动�?例如 USB 无线网卡出问题无法启用时，可以用 process.devcon 启用禁用网卡驱动进行修复�?参�?process.devcon 扩展库范例（ 扩展库管理器双击 process.devcon 可打开范例�?*/
import com.wmi;
for index,networkAdapter in com.wmi.each("SELECT * FROM Win32_NetworkAdapter WHERE NetConnectionId IS NOT NULL") {

    console.log(networkAdapter.GUID) //网卡 GUID
    console.log(networkAdapter.PNPDeviceID)  //网卡设备实例 ID，前面加一个@字符可作�?process.devcon 的参数禁用设�?    console.log(networkAdapter.NetEnabled) //网卡是否启用
    console.log(networkAdapter.ProductName)  //网卡�?    console.log(networkAdapter.NetConnectionId ) //网卡连接�?
    networkAdapter.Disable(); //禁用网卡
    console.log( networkAdapter.NetConnectionId + " Disabled")
}

process.explore("shell:::{7007ACC7-3202-11D1-AAD2-00805FC1270E}");
console.pause();

for index,networkAdapter in com.wmi.each("SELECT * FROM Win32_NetworkAdapter WHERE NetConnectionId IS NOT NULL") {
    networkAdapter.Enable();
    console.log( networkAdapter.NetConnectionId + " Enabled")
}

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/Manage/wmi.network.md)

