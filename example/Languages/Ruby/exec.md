[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鎵цRuby浠ｇ爜

```aardio aardio
//鎵цRuby浠ｇ爜
import win.ui;
/*DSG{{*/
var winform = win.form(text="鎵цRuby浠ｇ爜";right=759;bottom=469)
winform.add(
edit={cls="edit";left=26;top=16;right=737;bottom=435;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;z=1}
)
/*}}*/

import process.ruby;
var out = process.ruby.exec("puts '娴嬭瘯UTF-8'")
winform.edit.print(out);

var out = process.ruby.eval(`[1, 2, { name: "tanaka", age: 19 }]`)
winform.edit.print(out);

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Ruby/exec.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Ruby/exec.md')

