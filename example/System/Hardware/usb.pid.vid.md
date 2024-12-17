[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: PID,VID

```aardio aardio
//PID,VID
import console;
import sys.device;

// 鍒涘缓涓�涓?USB 璁惧瀵硅薄,鍙傛暟涓?_GUID_DEVCLASS_USB
var usbDevices = sys.device("{36FC9E60-C465-11CF-8056-444553540000}");

// 閬嶅巻鎵�鏈?USB 璁惧
for(index, classGuid, deviceDesc, hardwareId,friendlyName in usbDevices.each(
    8/*_SPDRP_CLASSGUID*/,
    0/*_SPDRP_DEVICEDESC*/,
    1/*_SPDRP_HARDWAREID*/,
    0xC/*_SPDRP_FRIENDLYNAME*/,
)) {
    // 瑙ｆ瀽纭欢 ID 鑾峰彇 VID 鍜?PID
    if(#hardwareId) {
        var vid, pid = string.match(hardwareId[1], "VID_(\x+)&PID_(\x+)");
        if(vid && pid) {
            console.log("VID:", vid);
            console.log("PID:", pid);
            console.log("璁惧鎻忚堪",deviceDesc);
            console.log("鍙嬪ソ鍚嶇О",friendlyName);
            console.more(1);
        }
    }
}

console.pause(true);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Hardware/usb.pid.vid.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Hardware/usb.pid.vid.md')

