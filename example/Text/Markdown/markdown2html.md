[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: markdown 转换�?HTML

````aardio aardio
//markdown 转换�?HTML

var md = /*
# 列表

1. 列表�?2. 列表�?    - 嵌套列表
    - 嵌套列表

# 表格

| foo | bar |
| --- | ---: |
| baz | bim |

# 代码�?
```aardio
print("你好�?);
```
*/

import string.markdown;
var markdown = string.markdown();

var html = markdown.render(md);
print(html);

````

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Text/Markdown/markdown2html.md)

