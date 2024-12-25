[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 字符串列�?
```aardio aardio
//字符串列�?import console;

import string.list;
tlist = string.list();

tlist.load("/可从指定文件加载.lst")

tlist.a = 123;
tlist.b = 456;
tlist.c = 789;

console.log( tlist.find("b") )

for i,k,v in tlist.each() {
    console.log("顺序:"+i,"名字:"+k,"�?"+v )
}

tlist.save("/可保存到文件.lst")

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/Config/stringlist.md)

