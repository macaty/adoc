[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: fsys.table

```aardio aardio
//fsys.table
import console;
import fsys.table;

var setting = fsys.table("/setting.table")
setting.load(); //从文件载入表

//读写成员,象普通table 对象一样使�?setting.a = 123;
setting.b = 456;

//混入成员到配置表
setting.mixin(
    c = {a=1;b=2};
    d = 123;
    e = raw.buffer(5,"abc")
)

//保存配置�?setting.save()

setting2 = fsys.table("/setting.table")
setting2.load(); //读取

for(k,v in setting2){
    console.log(k,v ) //象普通table对象一样使�?}

console.log( setting2 ) //转换为字符串

execute("pause")

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/Config/fsys.table.md)

