[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 绐楀彛绋嬪簭 - 閬僵鏁堟灉

```aardio aardio
//绐楀彛绋嬪簭 - 閬僵鏁堟灉
import win.ui;
/*DSG{{*/
var winform = win.form(text="閬僵绀轰緥";right=759;bottom=469)
winform.add(
button={cls="button";text="鏄剧ず閬僵";left=416;top=80;right=624;bottom=160;z=1};
edit={cls="edit";text="edit";left=112;top=192;right=528;bottom=304;edge=1;multiline=1;z=2}
)
/*}}*/

import win.ui.mask;
var frmMask = win.ui.mask(winform,true)
winform.button.oncommand = function(id,event){
    winform.button.disabledText = "绐楀彛瀹㈡埛鍖虹鐢ㄤ腑..."
    frmMask.show(true); //鏄剧ず閬僵

    win.delay(2000);
    winform.button.disabledText = null;
    frmMask.show(false); //闅愯棌閬僵
}

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Effects/mask.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Effects/mask.md')

