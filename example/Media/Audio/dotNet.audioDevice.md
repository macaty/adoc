[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 切换输出设备

```aardio aardio
//切换输出设备
import console;
import dotNet.audioDevice;

var defRenderId = dotNet.audioDevice.getDefaultRenderId();
var defCaptureId = dotNet.audioDevice.getDefaultCaptureId();

for( dev,devId,devName in dotNet.audioDevice.each() ){
    if(devId == defRenderId) console.writeText("默认音频输出设备");
    if(devId == defCaptureId) console.writeText("默认录音设备");

    console.log(devId,devName);
    if(!string.find(devName,"XGIMI") ){
        dotNet.audioDevice.setDefault(devId);
    }
}

console.pause(true);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Media/Audio/dotNet.audioDevice.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Media/Audio/dotNet.audioDevice.md')
