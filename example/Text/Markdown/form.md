[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: Markdown 绐楀彛鎺т欢

````aardio aardio
//Markdown 绐楀彛鎺т欢
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Text/Markdown/form.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Text/Markdown/form.md')

