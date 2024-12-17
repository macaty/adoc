[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 绐楀彛婊氬姩鏉?
```aardio aardio
//绐楀彛婊氬姩鏉?import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=469)
winform.add(
button={cls="button";text="button";left=118;top=73;right=260;bottom=120;ah=1;aw=1;z=1};
button2={cls="button";text="button2";left=107;top=397;right=356;bottom=530;ah=1;aw=1;z=2}
)
/*}}*/

import win.ui.scrollbar;
var vScrollBar = win.ui.scrollbar(winform,true);

vScrollBar.adjust = function( cx,cy,wParam ) {
    var scaleX,scaleY = winform.getScale();

    vScrollBar.line = 1 * scaleY;
    vScrollBar.setRange(1,100 * scaleY ,16);
};

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Controls/scrollWindow.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Controls/scrollWindow.md')

