[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: process.python - 鎸囧畾鍚姩鍙傛暟

```aardio aardio
//鎸囧畾鍚姩鍙傛暟
import win.ui;
/*DSG{{*/
var winform = win.form(text="process.python - 鎸囧畾鍚姩鍙傛暟";right=759;bottom=469)
winform.add(
edit={cls="edit";left=16;top=22;right=722;bottom=420;edge=1;multiline=1;z=1}
)
/*}}*/

import process.python;

/*
鎵ц Python 浠ｇ爜
鍙寚瀹氫竴涓垨澶氫釜鍚姩鍙傛暟锛屼篃鍙互鐢ㄤ竴涓瓧绗︿覆鍖呭惈澶氫釜鍙傛暟锛堢┖鏍煎垎闅旓級
*/
var python = process.python.exec(`
import sys
print( sys.argv )
`,"鍙傛暟1","鍙傛暟2");

python.logResponse(winform.edit);

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python AnyVersion/argv.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python AnyVersion/argv.md')

