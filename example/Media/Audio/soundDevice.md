[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鑾峰彇澹板崱

```aardio aardio
//鑾峰彇澹板崱
import win.ui;
/*DSG{{*/
var winform = win.form(text="鑾峰彇澹板崱";right=575;bottom=319;border="dialog frame";max=false;min=false)
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
    winform.edit.print("澹板崱椹卞姩鐗堟湰锛?,tostring(fsys.version( outcaps.vDriverVersion << 16 )) )

    import sys.soundDevice;
    sys.soundDevice.enum(
        function(description,dataFlow,dataType,deviceId,module,interface,waveDeviceId){
            if( !dataFlow ){
                winform.edit.print(description); //鏄剧ず澹板崱瀹屾暣鍚嶇О
                return false;
            }
            return true;
        }
    )
}
else {
    winform.edit.print("娌℃湁鎵惧埌澹板崱")
}

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Media/Audio/soundDevice.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Media/Audio/soundDevice.md')

