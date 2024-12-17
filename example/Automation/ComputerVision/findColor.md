[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 灞忓箷鎵捐壊

```aardio aardio
//灞忓箷鎵捐壊
import gdi;
import win;
import mouse;
import soImage;
import winex;

//鏌ユ壘绐楀彛
var hwndParent = winex.find("Afx\:\x+\:\x+\:\x+\:\x+\:\x+"," 鍓湰");
var hwnd = winex.findEx(hwndParent,,"Afx\:RibbonBar\:\x+\:\x+\:\x+\:\x+","aardio ");
mouse.moveToWindow(0,0,hwnd);

//鎶撳睆
var imgScreen = soImage();
imgScreen.captureWindow(hwnd);

//鍦ㄥ浘鍍忎笂鎼滅储鎸囧畾棰滆壊鐨勭偣,
//绗竴涓弬鏁版槸涓�涓〃绀烘煡鎵鹃鑹茬殑鏁板�?鏇村鍙傛暟鐢ㄦ硶璇锋煡鐪嬫櫤鑳芥彁绀?var x,y = imgScreen.findColor( gdi.RGB(48,171,53) );

//绉诲姩榧犳爣鍒版寚瀹氫綅缃紝鏄剧ず榧犳爣杞ㄨ抗
mouse.moveToWindow(x,y,hwnd,8);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Automation/ComputerVision/findColor.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Automation/ComputerVision/findColor.md')

