[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: WMI 获取系统信息

```aardio aardio
//WMI 获取系统信息
//参�?https://bbs.aardio.com/forum.php?mod=viewthread&tid=2477
//相关范例: 范例\操作系统\系统版本信息;范例\操作系统\硬件信息\查询硬件信息
import console;
import com.wmi;
var osInfo = com.wmi.get("SELECT * FROM Win32_OperatingSystem");
console.log(osInfo.Caption());//操作系统
console.log(osInfo.Version());//版本
console.more();

import sys.cpu;
var cpu = sys.cpu.getInfoByWmi()
console.log(cpu.DeviceID);//CPU
console.log(cpu.Name);//
console.log("CPU 核心数：",cpu.NumberOfCores);
console.log("CPU 逻辑核心数：", cpu.NumberOfLogicalProcessors);
console.log("CPU 最大速度�?, math.round(cpu.MaxClockSpeed/1000,2) + "GHz");
console.log("CPU 当前速度�?, math.round(cpu.CurrentClockSpeed/1000,2) + "GHz");
console.log("CPU 位宽�? ,cpu.AddressWidth);
console.more()

import sys.tpmInfo;
var tpmInfo = sys.tpmInfo.get();

if(tpmInfo){
    console.log("支持 TPM");
    console.log("TPM 是否启用�?,tpmInfo.enabled);
    console.log("TPM 是否激活：",tpmInfo.activated);
    console.log("TPM 支持版本�?,tpmInfo.version)
}
else {
    console.log("不支�?TPM");
}
console.more();

for index,mem in com.wmi.each("win32_physicalmemory") {
    console.log("内存容量",..math.size64(mem.capacity()).format());
}
console.more();

var wmi = com.wmi();
var display = wmi.instancesof("Win32_videocontroller")
for index, video in com.each(display) {
    console.log(video.DeviceId);//显示�?    console.log(video.Name);
    console.log(math.size64(video.AdapterRAM).format())
}
console.more();

var colItems = wmi.ExecQuery("SELECT * FROM Win32_NetworkAdapterConfiguration WHERE IPEnabled=true",null,48)
if(colItems){
    for index, item in com.each(colItems) {
        console.log(item.Description());//网卡
        console.log(item.DefaultIPGateway(0));//默认网关�?        console.log(item.DNSHostName(0));//计算机名
        console.log(item.IPAddress(0));//IP地址
        console.log(item.DNSServerSearchOrder(0));//默认 DNS
        console.log(item.IPSubnet(0));//子网掩码
        console.log(item.MACAddress());//M AC地址
    }
}
console.more();

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/COM/WMI/SysInfo.md)

