[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 纭欢淇℃伅

```aardio aardio
//纭欢淇℃伅
//鐩稿叧鑼冧緥: 鑼冧緥\COM 缁勪欢\WMI\鑾峰彇绯荤粺淇℃伅;鑼冧緥\鎿嶄綔绯荤粺\绯荤粺鐗堟湰淇℃伅

import console;

import sys.baseBoard;
console.log("涓绘澘",sys.baseBoard.getFullName())

import sys.cpu;
console.log("CPU:",sys.cpu.getBrand());
console.log("CPU 褰撳墠閫熷害:",sys.cpu.getFrequence(true));

var cpu = sys.cpu.getInfoByWmi()
console.log(cpu.DeviceID );//CPU
console.log(cpu.Name);//
console.log("CPU 鏍稿績鏁帮細"+ cpu.NumberOfLogicalProcessors);
console.log("CPU 閫昏緫鏍稿績鏁帮細"+ cpu.NumberOfLogicalProcessors);
console.log("CPU 鏈�澶ч�熷害锛?+ math.round(cpu.MaxClockSpeed/1000,2) + "GHz");
console.log("CPU 褰撳墠閫熷害锛?+ math.round(cpu.CurrentClockSpeed/1000,2) + "GHz");
console.log("CPU 浣嶅锛? + cpu.AddressWidth);
console.more()

import sys.mem;
console.log("Total Memory:",sys.mem.getInfo().totalPhys.formatSize);

import sys.display;
console.log("Display Adapter:",sys.display.getAdapter().Description)

import sys.device;
var devInfo = sys.device(/*"{4d36e96c-e325-11ce-bfc1-08002be10318}"*/,"PCI");
for( index,classGuid,deviceDesc in devInfo.each(
    8/*_SPDRP_CLASSGUID*/,
    0/*_SPDRP_DEVICEDESC*/
    ) ){
    console.log( index,classGuid,deviceDesc );
}

//鏌ユ壘 USB 缃戝崱
var devices = sys.device("{4d36e972-e325-11ce-bfc1-08002be10318}"/*_GUID_DEVCLASS_NET*/,"USB");
for( index,classGuid,deviceDesc,hardwareId in devices.each(
    8/*_SPDRP_CLASSGUID*/,
    0/*_SPDRP_DEVICEDESC*/,
    1/*_SPDRP_HARDWAREID*/
    ) ){

    console.log( index,classGuid,deviceDesc,hardwareId[1] );
}

/*
鐩稿叧鑼冧緥锛?鑼冧緥\COM 缁勪欢\WMI\鑾峰彇绯荤粺淇℃伅
鑼冧緥\鎿嶄綔绯荤粺\纭欢淇℃伅\鏌ヨ纭欢淇℃伅
*/

console.pause(true);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Hardware/device.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Hardware/device.md')

