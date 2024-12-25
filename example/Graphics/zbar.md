[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 二维码识别工�?
```aardio aardio
//二维码识别工�?import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="二维码识别工�?;right=477;bottom=275;bgcolor=16777215;border="dialog frame";exmode="none";max=false;mode="popup";topmost=1)
winform.add(
btnScanClipBD={cls="plus";text="自剪贴板识别";left=155;top=231;right=303;bottom=261;align="left";bgcolor=-5197169;db=1;dl=1;dr=1;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=20}};iconText='\uF0EA';notify=1;textPadding={left=39};z=2};
btnScanScreen={cls="plus";text="自屏幕识�?;left=310;top=231;right=447;bottom=261;align="left";bgcolor=-5197169;db=1;dr=1;font=LOGFONT(h=-16);foreRight=13;iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=20}};iconText='\uF108';notify=1;textPadding={left=39};z=3};
edit={cls="edit";left=15;top=32;right=465;bottom=220;autohscroll=false;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;z=1};
static={cls="static";text="复制二维码自动识别，也可以直接拖放二维码图像到此窗口";left=16;top=7;right=436;bottom=28;color=3947580;dl=1;dr=1;dt=1;transparent=1;z=4}
)
/*}}*/

import zbar;
import win.clip.viewer;
winform.clipViewer = win.clip.viewer(winform);

var scanner = zbar.scanner();
scanner.config('qrcode.enable');
winform.clipViewer.onDrawClipboard = function(){
    winform.btnScanClipBD.oncommand();
}

import win.clip.bitmap;
winform.btnScanClipBD.oncommand = function(id,event){
    winform.edit.text = "";

    var bmp = win.clip.bitmap.read()
    if(bmp){
        scanner.scanBitmap(bmp,function(typeName,data){
            //二维码应当总是使用 UTF-8 编码
            if(!string.isUtf8(data)){
                data = string.fromto(data,936,65001);
            }

            winform.edit.text = data;
        })
    }
}

import com.picture;
winform.btnScanScreen.oncommand = function(id,event){
    winform.edit.text = "";

    scanner.scanBitmap(com.picture.snap(),function(typeName,data){
        //二维码应当总是使用 UTF-8 编码
        if(!string.isUtf8(data)){
            data = string.fromto(data,936,65001);
        }

        winform.edit.text = data;
    })
}

winform.onDropFiles = function(files){
    var bmp = gdip.bitmap(files[1])
    if(bmp){
        scanner.scanBitmap(bmp,function(typeName,data){
            winform.edit.text = data;
        })
    }
}

winform.clipViewer.onDrawClipboard();

winform.btnScanScreen.skin({
    background={
        default=0x668FB2B0;
        disabled=0xFFCCCCCC;
        hover=0xFF928BB3
    };
    color={
        default=0xFF000000;
        disabled=0xFF6D6D6D
    }
})

winform.btnScanClipBD.skin({
    background={
        default=0x668FB2B0;
        disabled=0xFFCCCCCC;
        hover=0xFF928BB3
    };
    color={
        default=0xFF000000;
        disabled=0xFF6D6D6D
    }
})

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Graphics/zbar.md)

