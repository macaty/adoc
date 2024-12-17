[aardio 鏂囨。](../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 浜岀淮鐮佺敓鎴愬伐鍏?
```aardio aardio
//浜岀淮鐮佺敓鎴愬伐鍏?
import win.ui;
/*DSG{{*/
var winform = win.form(text="浜岀淮鐮佺敓鎴愬伐鍏?;right=851;bottom=775)
winform.add(
btnQrEnode={cls="button";text="鐢熸垚浜岀淮鐮?;left=655;top=630;right=797;bottom=672;db=1;dr=1;z=2};
edit={cls="edit";text="http://bbs.aardio.com";left=69;top=633;right=622;bottom=670;db=1;dl=1;dr=1;edge=1;multiline=1;z=9};
lbErrLevel={cls="static";text=" 0锛歀 鍙籂閿?%鏁版嵁鐮佸瓧";left=129;top=735;right=297;bottom=758;db=1;dl=1;transparent=1;z=7};
lbVersion={cls="static";text="鑷姩閫夋嫨鐗堟湰";left=491;top=735;right=697;bottom=758;db=1;dl=1;dr=1;transparent=1;z=8};
plus={cls="plus";left=71;top=50;right=786;bottom=588;db=1;dl=1;dr=1;dt=1;repeat="scale";z=1};
static={cls="static";text="绾犻敊绾у埆:";left=38;top=703;right=122;bottom=730;align="right";db=1;dl=1;transparent=1;z=4};
static2={cls="static";text="鐗堟湰(澶у皬):";left=378;top=703;right=462;bottom=730;align="right";db=1;dl=1;transparent=1;z=6};
tbErrLevel={cls="trackbar";left=121;top=690;right=315;bottom=720;db=1;dl=1;max=3;min=0;z=3};
tbVersion={cls="trackbar";left=464;top=690;right=728;bottom=720;db=1;dl=1;dr=1;max=40;min=0;z=5}
)
/*}}*/

winform.tbErrLevel.oncommand = function(id,event,pos){

    if( event == 0x8/*_TB_ENDTRACK*/ ){
        pos = winform.tbErrLevel.pos;
        var v = {[0]="L 鍙籂閿?%鏁版嵁鐮佸瓧";[1]="M 鍙籂閿?5%鐨勬暟鎹爜瀛?;[2]="Q 鍙籂閿?5%鐨勬暟鎹爜瀛?;[3]="H 鍙籂閿?0%鐨勬暟鎹爜瀛?;}
        winform.lbErrLevel.text = pos +"锛?+ v[pos];
    }
}

winform.tbVersion.oncommand = function(id,event,pos){
    if( event == 0x8/*_TB_ENDTRACK*/ ){
        pos = winform.tbVersion.pos;
        if(!pos)winform.lbVersion.text = "鑷姩閫夋嫨鐗堟湰";
        else {
            var width = ((pos-1)*4)+21;
            winform.lbVersion.text = string.format("鐗堟湰:%d 浜岀淮鐮佹暟鎹ぇ灏?%d x %d",pos,width,width );
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Graphics/qrcode.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Graphics/qrcode.md')

