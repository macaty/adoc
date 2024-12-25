[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 格式化HTML

```aardio aardio
//格式�?import win.ui;
/*DSG{{*/
var winform = win.form(text="格式化HTML";right=1059;bottom=736)
winform.add(
button={cls="button";text="格式化HTML";left=847;top=697;right=957;bottom=731;z=2};
editHtml={cls="richedit";left=6;top=8;right=1049;bottom=691;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;link=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

import string.html;
winform.button.oncommand = function(id,event){
    var htmlDoc = string.html(winform.editHtml.text);
    winform.editHtml.text = htmlDoc.outerXml(true);
}

winform.editHtml.limit = 0xFFFFFFFF

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/HTML/format.md)

