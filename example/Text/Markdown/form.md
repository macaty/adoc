[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: Markdown 窗口控件

````aardio aardio
//Markdown 窗口控件
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=469)
winform.add()
/*}}*/

import web.form.simpleMarkdown;
var wb = web.form.simpleMarkdown(winform);
winform.show();

var markdown = /*
# hello, markdown!

| Syntax      | Description |
| ----------- | -----------: |
| Header      | Title       |
| Paragraph   | Text        |

```aardio
for(i=1;10;1){
    print(i);
}

```
*/

wb.write(markdown);

win.loopMessage();

````

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Text/Markdown/form.md)

