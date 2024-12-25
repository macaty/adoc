[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Showdown 解析 Markdown �?HTML

````aardio aardio
//调用 Showdown 解析 Markdown �?HTML
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
print("你好");
```
*/

import web.script.showdown;
var showdown = web.script.showdown;

//创建 Markdown 解析�?var converter = showdown.Converter({ tasklists:true });

//解析 Markdown 并返�?HTML
var html= converter.makeHtml(text);

//在控制台输出结果
console.log(html);

console.pause();

````

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Text/Markdown/showdown.md)

