[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 绐楀彛绋嬪簭 - 閫氱煡绐楀彛

```aardio aardio
//绐楀彛绋嬪簭 - 閫氱煡绐楀彛
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=208;bottom=150;bgcolor=15780518;border="none";exmode="toolwindow";topmost=1)
winform.add(
button={cls="button";text="r";left=179;top=1;right=201;bottom=18;font=LOGFONT(name='Marlett';charset=2;weight=500);z=1};
static={cls="static";text="static";left=30;top=43;right=162;bottom=72;transparent=1;z=2}
)
/*}}*/

import win.util.popup

//浣跨獥鍙ｅ湪灞忓箷鍙充笅瑙掑脊鍑?pop = win.util.popup(winform)
pop.countdown=function(remaintime){
    winform.static.text = "鍓╀綑鏃堕棿锛? + remaintime  + "绉?
}

winform.button.oncommand = function(id,event){
    winform.close();

}//endproc
winform.show(true)
win.loopMessage();
return winform;

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Effects/popup.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Effects/popup.md')

