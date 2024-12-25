[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 中文分词

```aardio aardio
//中文分词
import win.ui;
/*DSG{{*/
var winform = win.form(text="mmseg test";right=759;bottom=469)
winform.add(
richedit={cls="richedit";left=38;top=33;right=723;bottom=423;bgcolor=16777215;edge=1;hscroll=1;multiline=1;vscroll=1;wrap=1;z=1}
)
/*}}*/

import mmseg
var str = /*
MMSEG（Maximum Matching Segmentation）是一种高效的中文分词算法，它采用了最长匹配原则，能够有效地处理歧义问题，适用于多种应用场景，如搜索引擎、信息检索等
*/

//加词，也可以�?mmseg.loadWords 加载词典文件
mmseg.addWord("应用场景")

for word,attr in mmseg.each(str){
    winform.richedit.appendText( word," " )
}

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Text/mmseg.md)

