[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 获取声卡

```aardio aardio
//获取声卡
import win.ui;
/*DSG{{*/
var winform = win.form(text="获取声卡";right=575;bottom=319;border="dialog frame";max=false;min=false)
winform.add(
edit={cls="edit";left=8;top=8;right=566;bottom=308;edge=1;multiline=1;z=1}
)
/*}}*/

class WAVEOUTCAPS {
    WORD wMid;
    WORD wPid;
    INT vDriverVersion;
    WORD szPname[0x20/*_MAXPNAMELEN*/];
    INT dwFormats;
    WORD wChannels;
    WORD wReserved1;
    INT dwSupport;
} ;

::Winmm :=  raw.loadDll("Winmm.dll");
var outcaps = WAVEOUTCAPS();

if(  0/*_MMSYSERR_NOERROR*/= ::Winmm.waveOutGetDevCapsW(0,outcaps,raw.sizeof(outcaps)) ){
    import fsys.version;
    winform.edit.print("声卡驱动版本�?,tostring(fsys.version( outcaps.vDriverVersion << 16 )) )

    import sys.soundDevice;
    sys.soundDevice.enum(
        function(description,dataFlow,dataType,deviceId,module,interface,waveDeviceId){
            if( !dataFlow ){
                winform.edit.print(description); //显示声卡完整名称
                return false;
            }
            return true;
        }
    )
}
else {
    winform.edit.print("没有找到声卡")
}

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Media/Audio/soundDevice.md)

