[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鏍煎紡鍖朒TML

```aardio aardio
//鏍煎紡鍖?import win.ui;
/*DSG{{*/
var winform = win.form(text="鏍煎紡鍖朒TML";right=1059;bottom=736)
winform.add(
button={cls="button";text="鏍煎紡鍖朒TML";left=847;top=697;right=957;bottom=731;z=2};
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/HTML/format.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/HTML/format.md')

