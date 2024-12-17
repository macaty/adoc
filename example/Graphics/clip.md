[aardio 鏂囨。](../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鍓创鏉垮浘鍍?
```aardio aardio
//鍓创鏉垮浘鍍?import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=637;bottom=450;)
winform.add(
btnRead={cls="button";text="璇诲彇鍓创鏉垮浘鍍?;left=249;top=379;right=404;bottom=419;db=1;dr=1;z=3};
btnWrite={cls="button";text="鎴睆骞跺啓鍏ュ壀璐存澘";left=428;top=379;right=598;bottom=419;db=1;dr=1;z=2};
picturebox={cls="plus";left=21;top=16;right=617;bottom=360;db=1;dl=1;dr=1;dt=1;edge=1;repeat="scale";transparent=1;z=1}
)
/*}}*/

import win.clip;
import process.imageView;
import gdip.bitmap;

winform.btnRead.oncommand = function(id,event){
    var hBmp = win.clip.readBitmap()
    if(!hBmp){
        return winform.msgboxErr("鍓创鏉挎病鏈夊浘鍍?);
    }

    //瀛樹负鍥惧儚鏂囦欢
    com.picture.fromBitmap(hBmp).Save("/clip.jpg")

    //杞崲涓?GDI+ 鍥惧儚
    var bmp = gdip.bitmap(hBmp);
    winform.picturebox.background = bmp;

    //瀛樹负鍥惧儚鏂囦欢
    bmp.save("/clip.jpg")

    //瀛樹负 16 浣?BMP 鏂囦欢
    var bmp16 = bmp.clone(,,,,0x21005/*_PixelFormat16bppRGB555*/);
    bmp16.save("/16.bmp");

    //棰勮鍥惧儚
    process.imageView("/clip.jpg")
}

import gdip.snap;
winform.btnWrite.oncommand = function(id,event){

    //鎴睆
    var bmp = gdip.snap();

    //鏄剧ず鍥惧儚
    winform.picturebox.background = bmp;

    //鑾峰彇浣嶅浘鍙ユ焺
    var hBmp = bmp.copyHandle();

    //鍐欏叆鍓创鏉?    win.clip.writeBitmap(
        hBmp, //浣嶅浘鍙ユ焺
        true, //璁╁壀璐存澘鎺ョ浣嶅浘锛屼篃灏变笉鐢ㄥ啀澶嶅埗锛屼篃涓嶇敤鍐嶉噴鏀?hBmp 浜?        true //娓呯┖鍓创鏉夸腑鍏朵粬鏍煎紡鏁版嵁
    );

    //濡傛灉涓婇潰鐨勫弬鏁?@2 涓嶆槸 true锛屽氨瑕佺敤涓嬮潰鐨勪唬鐮侀噴鏀句綅鍥?    //::DeleteObject(hBmp);
}

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Graphics/clip.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Graphics/clip.md')

