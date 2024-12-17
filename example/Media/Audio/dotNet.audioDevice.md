[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鍒囨崲杈撳嚭璁惧

```aardio aardio
//鍒囨崲杈撳嚭璁惧
import console;
import dotNet.audioDevice;

var defRenderId = dotNet.audioDevice.getDefaultRenderId();
var defCaptureId = dotNet.audioDevice.getDefaultCaptureId();

for( dev,devId,devName in dotNet.audioDevice.each() ){
    if(devId == defRenderId) console.writeText("榛樿闊抽杈撳嚭璁惧");
    if(devId == defCaptureId) console.writeText("榛樿褰曢煶璁惧");

    console.log(devId,devName);
    if(!string.find(devName,"XGIMI") ){
        dotNet.audioDevice.setDefault(devId);
    }
}

console.pause(true);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Media/Audio/dotNet.audioDevice.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Media/Audio/dotNet.audioDevice.md')

