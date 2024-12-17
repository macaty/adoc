[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 褰曢煶锛圢Audio锛?
```aardio aardio
//褰曢煶锛圢Audio锛?import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="褰曢煶";right=382;bottom=201)
winform.add(
btnPlay={cls="plus";text="鎾斁";left=59;top=132;right=156;bottom=162;align="left";color=3947580;dl=1;dt=1;font=LOGFONT(h=-13);iconColor=32768;iconStyle={align="left";font=LOGFONT(h=-16;name='FontAwesome')};iconText='\uF027';notify=1;textPadding={left=20};z=3};
btnRecord={cls="plus";text="褰曢煶";left=59;top=84;right=196;bottom=115;align="left";dl=1;dt=1;font=LOGFONT(h=-14);iconColor=17151;iconStyle={align="left";font=LOGFONT(h=-14;name='FontAwesome')};iconText='\uF130';notify=1;textPadding={left=20};z=1};
cmbDevices={cls="combobox";left=59;top=25;right=264;bottom=51;dl=1;dt=1;edge=1;items={};mode="dropdown";z=2};
recordingLevelMeter={cls="plus";left=23;top=25;right=31;bottom=156;bgcolor=6447459;db=1;dl=1;dt=1;forecolor=17151;hide=1;notify=1;z=4}
)
/*}}*/

import dotNet.audio;
winform.recordingLevelMeter.setProgressRange(1,100);
dotNet.audio.onWaveIn = function(max){
    winform.recordingLevelMeter.progressPos = max * 100;
}

var devices = {"绯荤粺澹伴煶"};
for deviceNumber,deviceName,caps in dotNet.audio.eachWaveInDevice(){
    table.push(devices,deviceName);
}

winform.cmbDevices.items = devices;
winform.cmbDevices.selIndex = 1;

import fsys.media;
winform.btnRecord.oncommand = function(id,event){
    fsys.media.playSound(null);

    if(winform.btnRecord.checked){
        var deviceNumber = winform.cmbDevices.selIndex - 3;
        dotNet.audio.startWaveIn("/test.wav",deviceNumber);
        winform.btnPlay.disabled = true;

        winform.recordingLevelMeter.hide = false;
    }
    else {
        dotNet.audio.stopWaveIn();
        winform.btnPlay.disabled = false;
        winform.recordingLevelMeter.hide = true;
    }
}

import fsys.media;
winform.btnPlay.oncommand = function(id,event){
    winform.recordingLevelMeter.hide = false;
    fsys.media.playSound("/test.wav");
    dotNet.audio.startWaveIn();
}
winform.btnPlay.disabled = true;

winform.btnPlay.skin({
    color={
        active=0xFF00FF00;
        default=0xFF3C3C3C;
        disabled=0xFF6D6D6D;
        hover=0xFFFF0000
    }
    iconColor = {
        default=0xFF008000;
        disabled=0xFF6D6D6D;
    }
})

winform.btnRecord.skin({
    color={
        active=0xFF00FF00;
        default=0xFF000000;
        disabled=0xEE666666;
        hover=0xFFFF0000
    };
    checked={
        iconColor={default=0xFFff4200};
        iconText='\uF04D';
        text="鍋滄褰曢煶"
    }
})

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Media/Audio/dotNet.audio.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Media/Audio/dotNet.audio.md')

