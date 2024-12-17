[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: COM 鎺ュ彛 - 鎵弿浠?
```aardio aardio
//COM 鎺ュ彛 - 鎵弿浠?import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="璋冪敤鎵弿浠?;right=759;bottom=469)
winform.add(
plus={cls="plus";left=9;top=10;right=751;bottom=459;font=LOGFONT(h=-32;name='FontAwesome');repeat="scale";z=1}
)
/*}}*/

winform.show();
winform.plus.disabledText = {'\uF254';'\uF251';'\uF252';'\uF253';'\uF250'}

//鍒涘缓绾跨▼
thread.invoke(
    function(winform){
        import com;

        //https://learn.microsoft.com/zh-cn/previous-versions/windows/desktop/wiaaut/-wiaaut-commondialog
        var cdc = com.CreateObject("WIA.CommonDialog");
        var device = cdc.ShowSelectDevice(cdc.ScannerDeviceType,true,false);
        var scannerDevice = device.Items(1);

        //璁剧疆鎵弿浠睘鎬?        scannerDevice.setProperties("Horizontal Resolution",300);
        scannerDevice.setProperties("Vertical Resolution",300);
        scannerDevice.setProperties("Current Intent",scannerDevice.ColorIntent);

        /*
        //鏄剧ず鑾峰彇鍥惧儚瀵硅瘽妗?        var imageFile = cdc.ShowAcquireImage(cdc.ScannerDeviceType
            ,cdc.ColorIntent,cdc.MaximizeQuality, "{00000000-0000-0000-0000-000000000000}"
            ,true,true,false);
        */

        //鐩存帴鑾峰彇鍥惧儚
        var imageFile = scannerDevice.Transfer(cdc.wiaFormatJPEG);

        //https://learn.microsoft.com/zh-cn/previous-versions/windows/desktop/wiaaut/-wiaaut-iimagefile-filedata
        winform.plus.background = imageFile.FileData.BinaryData;
        winform.plus.disabledText = null;
    },winform
);

win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/Others/WIA.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/Others/WIA.md')

