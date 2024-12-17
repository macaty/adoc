[aardio 鏂囨。](../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 绐楀彛鑳屾櫙璐村浘

```aardio aardio
//鑳屾櫙璐村浘
import win.ui;
/*DSG{{*/
var winform = win.form(text="绐楀彛鑳屾櫙璐村浘";right=759;bottom=469)
winform.add(
bk={cls="bk";text="鏃犵獥鍙ｈ创鍥炬帶浠?;left=563;top=70;right=736;bottom=408;bgcolor=65535;z=3};
plus={cls="plus";left=72;top=66;right=498;bottom=288;bgcolor=32768;z=1};
plus2={cls="plus";left=14;top=164;right=440;bottom=386;bgcolor=8421504;z=2}
)
/*}}*/

/*
浣跨敤姝や簨浠跺彲浠ョ洿鎺ュ皢鑳屾櫙鐢诲埌缂撳瓨濂界殑浣嶅浘涓婁互鍚庯紝鐢盿ardio涓�娆¤緭鍑猴紝
濡傛灉涓嶆槸缁忓父鍙樺姩鐨勫浘鍍?鐩存帴鐢诲埌鑳屾櫙涓婂彲浠ラ伩鍏嶆坊鍔犲浣欑殑鎺т欢绐楀彛,閬垮厤绐楀彛闂寸殑閲嶅彔骞叉壈瀵艰嚧鐨勯棶棰樸�?*/
import gdip.graphics;
var bmp = com.picture.loadBitmap("~\extensions\wizard\project2\forms\images\winform.jpg");
winform.onDrawBackground  = function(hdc,rc){
    gdi.fillRect(hdc,0x00008C,rc.copy(,150));
    gdi.fillRect(hdc,0x468C00,rc.copy(200));

    //涔濆鏍艰创鍥?    gdi.drawBitmap(hdc,bmp,rc.move(200,150),140,140,100,225);

    var font = ::LOGFONT(weight=400;point=9;color=0xFF);
    gdi.drawTextCenter(hdc,font,"鏀瑰彉绐楀彛澶у皬璇曡瘯,浠绘剰浣嶇疆璐村浘閮藉彲浠ユ敮鎸佷節瀹牸",rc.move(120,150));
}

/*
鐢ㄤ笅闈㈢殑鍑芥暟璁﹑lus鐩存帴缁樺浘鍒扮獥鍙ｈ儗鏅笂
*/
winform.plus.directDrawBackgroundOnly();

winform.plus2.background = 0x90808080;
winform.plus.background = 0x90008000;

winform.disableDragFullWindow = false;

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Graphics/drawBackground.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Graphics/drawBackground.md')

