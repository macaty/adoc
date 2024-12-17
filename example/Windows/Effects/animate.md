[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 绐楀彛鍔ㄧ敾婕旂ず

```aardio aardio
//绐楀彛鍔ㄧ敾婕旂ず
import win.ui;
/*DSG{{*/
var winform = win.form(text="鍔ㄧ敾绐楀彛婕旂ず";right=400;bottom=202;max=false;min=false)
winform.add()
/*}}*/

import win.animate;
win.animate.fade( winform ).show()

winform.onClose = function(hwnd,message,wParam,lParam){
    win.animate.roll(winform).hide()
}

win.loopMessage();
return winform;

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Effects/animate.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Effects/animate.md')

