[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: RUNAS//绂佺敤璁惧

```aardio aardio
//RUNAS//绂佺敤璁惧
import console;
import sys.device;
import process.devcon;

//鏌ユ壘鎵�鏈夐紶鏍囪澶?var devices = sys.device("{4D36E96F-E325-11CE-BFC1-08002BE10318}"/*_GUID_DEVCLASS_MOUSE*/);

//閬嶅巻鎵惧埌鐨勯紶鏍囪澶?for( index,deviceDesc,hardwareId,T in devices.each(
    0/*_SPDRP_DEVICEDESC*/, //娣诲姞杩斿洖鍊?deviceDesc
    1/*_SPDRP_HARDWAREID*/ //娣诲姞杩斿洖鍊?hardwareId
    ) ){

    process.devcon.disable(hardwareId[1]);
}

console.pause(,"宸茬鐢ㄩ紶鏍囷紝鎸変换鎰忛敭鍚敤榧犳爣");

for( index,deviceDesc,hardwareId,T in devices.each(0,1) ){

    process.devcon.enable(hardwareId[1]);
}

console.pause(,"宸插惎鐢ㄩ紶鏍囷紝鎸変换鎰忛敭缁х画");

/*
//绂佺敤钃濈墮
var devices = sys.device("{E0CBF06C-CD8B-4647-BB8A-263B43F0F974}" );
for( index,deviceDesc,hardwareId in devices.each(0,1) ){
    process.devcon.disable(hardwareId[1]);
}
*/

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Hardware/devcon.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Hardware/devcon.md')

