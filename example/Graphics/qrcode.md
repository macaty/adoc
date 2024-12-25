[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 二维码生成工�?
```aardio aardio
//二维码生成工�?
import win.ui;
/*DSG{{*/
var winform = win.form(text="二维码生成工�?;right=851;bottom=775)
winform.add(
btnQrEnode={cls="button";text="生成二维�?;left=655;top=630;right=797;bottom=672;db=1;dr=1;z=2};
edit={cls="edit";text="http://bbs.aardio.com";left=69;top=633;right=622;bottom=670;db=1;dl=1;dr=1;edge=1;multiline=1;z=9};
lbErrLevel={cls="static";text=" 0：L 可纠�?%数据码字";left=129;top=735;right=297;bottom=758;db=1;dl=1;transparent=1;z=7};
lbVersion={cls="static";text="自动选择版本";left=491;top=735;right=697;bottom=758;db=1;dl=1;dr=1;transparent=1;z=8};
plus={cls="plus";left=71;top=50;right=786;bottom=588;db=1;dl=1;dr=1;dt=1;repeat="scale";z=1};
static={cls="static";text="纠错级别:";left=38;top=703;right=122;bottom=730;align="right";db=1;dl=1;transparent=1;z=4};
static2={cls="static";text="版本(大小):";left=378;top=703;right=462;bottom=730;align="right";db=1;dl=1;transparent=1;z=6};
tbErrLevel={cls="trackbar";left=121;top=690;right=315;bottom=720;db=1;dl=1;max=3;min=0;z=3};
tbVersion={cls="trackbar";left=464;top=690;right=728;bottom=720;db=1;dl=1;dr=1;max=40;min=0;z=5}
)
/*}}*/

winform.tbErrLevel.oncommand = function(id,event,pos){

    if( event == 0x8/*_TB_ENDTRACK*/ ){
        pos = winform.tbErrLevel.pos;
        var v = {[0]="L 可纠�?%数据码字";[1]="M 可纠�?5%的数据码�?;[2]="Q 可纠�?5%的数据码�?;[3]="H 可纠�?0%的数据码�?;}
        winform.lbErrLevel.text = pos +"�?+ v[pos];
    }
}

winform.tbVersion.oncommand = function(id,event,pos){
    if( event == 0x8/*_TB_ENDTRACK*/ ){
        pos = winform.tbVersion.pos;
        if(!pos)winform.lbVersion.text = "自动选择版本";
        else {
            var width = ((pos-1)*4)+21;
            winform.lbVersion.text = string.format("版本:%d 二维码数据大�?%d x %d",pos,width,width );
        }
    }
}

import qrencode.bitmap;
winform.btnQrEnode.oncommand = function(id,event){
    winform.plus.hide = true;
    var qrBmp = qrencode.bitmap(winform.edit.text,winform.tbVersion.pos,winform.tbErrLevel.pos );
    winform.plus.setBackground(qrBmp.copyBitmap(winform.plus.width));

    winform.plus.hide = false;
    winform.plus.redraw()
}

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Graphics/qrcode.md)

