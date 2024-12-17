[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 Showdown 瑙ｆ瀽 Markdown 涓?HTML

````aardio aardio
//璋冪敤 Showdown 瑙ｆ瀽 Markdown 涓?HTML
import console;

var text = /*
# hello, markdown!

| Syntax      | Description |
| ----------- | -----------: |
| Header      | Title       |
| Paragraph   | Text        |

- [x] This task is done
- [ ] This is still pending

```aardio
print("浣犲ソ");
```
*/

import web.script.showdown;
var showdown = web.script.showdown;

//鍒涘缓 Markdown 瑙ｆ瀽鍣?var converter = showdown.Converter({ tasklists:true });

//瑙ｆ瀽 Markdown 骞惰繑鍥?HTML
var html= converter.makeHtml(text);

//鍦ㄦ帶鍒跺彴杈撳嚭缁撴灉
console.log(html);

console.pause();

````

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Text/Markdown/showdown.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Text/Markdown/showdown.md')

