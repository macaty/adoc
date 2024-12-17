[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鏄剧ず鍣?DDC/CI

```aardio aardio
//鏄剧ず鍣?DDC/CI
//鏄剧ず鍣ㄦ帶鍒舵帴鍙ｏ紝涓嶆槸鎵�鏈夋樉绀哄櫒閮芥敮鎸?import console;
import sys.ddcci;

for ddcci in sys.ddcci.each() {
    console.dump(ddcci.capabilities,ddcci.description);
    if(!ddcci.capabilities.vcp) continue;

    ddcci.setPowerMode(4); //鍏冲睆
    sleep(1000);
    ddcci.setPowerMode(1); //浜睆
}

console.pause(true);

/*
import win.ui;
var winform = win.form( bgcolor=1;text="鏄剧ず鍣ㄥ潖鐐规娴? );

var colorIndex,color = 1;
var colorTable = { 1;0xFF0000;0x0000FF;0x00FF00;0xFFFFFF };

winform.onMouseDown = function(wParam,lParam){
    colorIndex,color = table.next(colorTable, colorIndex );
    if(!colorIndex) return winform.close();

    winform.bgcolor = color;
    winform.redrawBackground();
}

winform.show();
winform.fullscreen();
win.loopMessage();
*/

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Hardware/ddcci.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Hardware/ddcci.md')

