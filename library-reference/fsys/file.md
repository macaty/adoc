[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.file 库模块帮助文�?
## fsys 成员列表

### fsys.file("字符串参�?)

只读模式打开,文件必须存在

如果路径以斜杠结�?则以目录模式打开.

更多参数参考源�?
### fsys.file("字符串参�?,"a")

只写追加模式打开,创建新文件保留原文件

### fsys.file("字符串参�?,"a+")

读写追加模式打开,创建新文件保留原文件

### fsys.file("字符串参�?,"r+")

读写模式打开,文件必须存在

文件路径也可以指定一个目�?可使用返回对象读写目录时间属�?

更多参数参考源�?
### fsys.file("字符串参�?,"w")

只写模式打开,创建新文件清空原文件

### fsys.file("字符串参�?,"w+")

读写模式打开,创建新文件清空原文件

### fsys.file("字符串参�?,"w+D")

读写模式打开临时文件,关闭对象时自动删除文�?
### fsys.file()

[返回对象:fsysfileObject](#fsysfileObject)

### fsys.file(path,mode,shareMode,creation,flagsAndAttributes,secAttrib)

所有参数可�?

参数详细用法参考此函数源码与CreateFile参数用法,

mode参数可指定数值指定打开模式,也可使用与io.file相同规则的描述字�?
shareMode参数默认�?\_FILE\_SHARE\_READ \| \_FILE\_SHARE\_WRITE

creation参数默认值为 \_OPEN\_EXISTING

@flagsAndAttributes 为可选参数，指定文件属�?省略则自动设置此参数

@secAttrib 不必指定

### fsys.file(文件句柄)

可以指定文件、管道等句柄

### fsys.file(文件句柄,true)

直接文件、管道等句柄

添加析构函数负责释放句柄

## fsys.file 成员列表

用于打开或创建文件对�?

fsys.file 返回的文件对象可传入其他线程使用�?
### fsys.file.is()

判断参数是不是fsys.file对象

### fsys.file.lastModified()

参数 @1 指定文件路径，返回文件最后修改时间�?
返回值是 time.gmt 对象，即 RFC1123 格式时间。HTTP 协议使用该对�?
[返回对象:timeObject](../time/_.html#timeObject)

### fsys.file.lastModified(,"2024/1/1 11:01:00")

参数 @1 指定文件路径，\\b参数 @2 指定任何可作�?time.iso8601 参数的时间格式，可指定字符串�?
如果文件修改时间大于参数 @2 指定的时间则返回 true

### fsys.file.lines(path)

```aardio aardio
for line in fsys.file.lines(/*请输入逐行读取的文本文件路�?/) {

}

```

### fsys.file.temp()

[返回对象:fsysfileObject](#fsysfileObject)

### fsys.file.temp(pathOrExt,dontDeleteOnClose)

创建临时文件,

可选用 @pathOrExt 参数指定临时文件路径或后缀�?

指定临时文件后缀名时第一个字符必须是 . �?

可选指�?@dontDeleteOnClose 参数值为 true 禁止关闭对象自动删除文件,

@dontDeleteOnClose �?true 时文件才会有共享读写权限,

可通过返回文件对象�?path 属性获取临时文件路�?
## filefiletimesObject 成员列表

### filefiletimesObject.access

文件最后访问时�?
[返回对象:fsysTimeObject](#fsysTimeObject)

### filefiletimesObject.creation

文件创建时间

[返回对象:fsysTimeObject](#fsysTimeObject)

### filefiletimesObject.write

文件最后修改时�?
[返回对象:fsysTimeObject](#fsysTimeObject)

## filetimesObject 成员列表

### filetimesObject.access

文件最后访问时�?
[返回对象:timeObject](../time/_.html#timeObject)

### filetimesObject.creation

文件创建时间

[返回对象:timeObject](../time/_.html#timeObject)

### filetimesObject.write

文件最后修改时�?
[返回对象:timeObject](../time/_.html#timeObject)

## fsysfileObject 成员列表

### fsysfileObject.close()

关闭文件句柄

### fsysfileObject.delete()

关闭并删除文�?
### fsysfileObject.deviceIoControl

对设备驱动程序发送控制指�?
### fsysfileObject.deviceIoControl(控制�?输入结构�?输出结构�?

参数可以为空或结构体,

输出结构体也可以是raw.malloc分配的缓冲区,

成功返回true,以及读取的字节数

### fsysfileObject.flush()

刷新缓冲�?
### fsysfileObject.getFileTime()

返回创建时间、最后修改时间、最后访问时间，

所有返回时间为 UTC 标准时间

[返回对象:filefiletimesObject](#filefiletimesObject)

### fsysfileObject.getTime()

返回创建时间、最后修改时间、最后访问时间，

所有返回时间为 UTC 标准时间

[返回对象:filetimesObject](#filetimesObject)

### fsysfileObject.handle

返回文件句柄

### fsysfileObject.lastModified()

返回最后修改时�?返回值是time.gmt对象,

即RFC1123格式时间,HTTP协议使用该对�?
[返回对象:timeObject](../time/_.html#timeObject)

### fsysfileObject.path

返回文件路径

### fsysfileObject.read()

读取一行文�?
返回文本不包含回车换行符

### fsysfileObject.read(-1)

读取所有内容到文件尾部

### fsysfileObject.read(0)

是否未到达文件尾�?
如果已经到达文件尾返�?null，否则返回空字符串�?
注意在布尔表达式�?null 等于 false，空字符串等�?true�?
### fsysfileObject.read({int number} )

读取结构�?
不支持多参数

### fsysfileObject.read(字节�?

读取指定长度的字�?
不支持多参数

### fsysfileObject.readAll()

移动指针到文件头�?
读取到文件尾返回全部数据�?
改用 -1 为参数调�?read 函数可自当前位置读取到文件尾�?
### fsysfileObject.readBuffer

读取数据�?buffer ,成功返回读取长度,失败返回null

### fsysfileObject.readBuffer(buffer,读取长度)

直接读数据到内存

参数@1可以�?buffer 对象,或内存指�?

如果是指针则必须指定读取长度,否则长度参数可�?
成功返回读取长度

### fsysfileObject.readTo

读取直到以指定的字符串结�?
### fsysfileObject.readTo('结束�?)

读取直到以指定的字符串结�?返回值不包含结束�?

该函数每次仅读取一个字�?效率较低

### fsysfileObject.seek("cur",)

移动至相对当前位置的指定偏移量，

偏移量应当是一个普通数值�?
### fsysfileObject.seek("end")

移动指针至结束处

返回当前位置,返回值大�?GB则为负�?

获取文件大小推荐使用 size() 函数

### fsysfileObject.seek("end",)

移动至相对结束处的指定偏移量�?
偏移量应当是一个普通数值�?
### fsysfileObject.seek("set")

移动指针到开�?
### fsysfileObject.seek("set",)

移动至相对开始处的指定偏移量�?
偏移量应当是一个普通数值�?
普通数值的整数上限�?8PB，没有可能会写这么大的文件�?
所以偏移量不支持、也不必要使�?math.size64 对象

### fsysfileObject.seek()

得到当前位置

### fsysfileObject.setFileTime(creation=创建时间;access=访问时间;write=修改时间)

```aardio aardio
fsysfileObject.setFileTime(
    creation = fsys.time();
    access = fsys.time();
    write = fsys.time()
)

```

### fsysfileObject.setTime(creation=创建时间;access=访问时间;write=修改时间)

```aardio aardio
fsysfileObject.setTime(
    creation = time();
    access = time();
    write = time()
)

```

### fsysfileObject.seteof()

将当前文件位置设为文件末�?

用于快速改变文件大�?
成功返回true

### fsysfileObject.size()

返回文件大小�?
size 函数表示的容量可以达�?8PB，一般不必要 size64 函数�?
math.size64 对象主要用于格式化为适合单位表示的文本�?
### fsysfileObject.size64()

返回文件大小�?
返回值为 math.size64 长整数对象�?
可调用返回对象的 format 函数格式化为适合单位表示的文本�?
[返回对象:mathSize64Object](../math/_.html#mathSize64Object)

### fsysfileObject.type()

获取文件对象的类�?
例如控制台，管道，本地文�?...等等

返回值请参考\_FILE\_TYPE\_前缀的常�?
### fsysfileObject.write(字符�?

写入字符�?
参数也可以是数值、结构体

### fsysfileObject.writeBuffer

写入缓冲区数�?成功返回写入长度,失败返回null

### fsysfileObject.writeBuffer(buffer,写入长度)

直接写数据到内存

参数@1可以�?buffer 对象、字符串、内存指针�?
如果是指针则必须指定写入长度，否则长度参数可选�?
成功返回写入长度

### 自动完成常量

\_FILEOPENORD=0x600

\_FILE\_ATTRIBUTE\_ARCHIVE=0x20

\_FILE\_ATTRIBUTE\_COMPRESSED=0x800

\_FILE\_ATTRIBUTE\_DIRECTORY=0x10

\_FILE\_ATTRIBUTE\_HIDDEN=2

\_FILE\_ATTRIBUTE\_NORMAL=0x80

\_FILE\_ATTRIBUTE\_READONLY=1

\_FILE\_ATTRIBUTE\_SYSTEM=4

\_FILE\_ATTRIBUTE\_TEMPORARY=0x100

\_FILE\_BEGIN=0x0

\_FILE\_CASE\_PRESERVED\_NAMES=2

\_FILE\_CASE\_SENSITIVE\_SEARCH=1

\_FILE\_CURRENT=1

\_FILE\_END=2

\_FILE\_FILE\_COMPRESSION=0x10

\_FILE\_FLAG\_BACKUP\_SEMANTICS=0x2000000

\_FILE\_FLAG\_DELETE\_ON\_CLOSE=0x4000000

\_FILE\_FLAG\_NO\_BUFFERING=0x20000000

\_FILE\_FLAG\_OVERLAPPED=0x40000000

\_FILE\_FLAG\_POSIX\_SEMANTICS=0x1000000

\_FILE\_FLAG\_RANDOM\_ACCESS=0x10000000

\_FILE\_FLAG\_SEQUENTIAL\_SCAN=0x8000000

\_FILE\_FLAG\_WRITE\_THROUGH=0x80000000

\_FILE\_NOTIFY\_CHANGE\_ATTRIBUTES=4

\_FILE\_NOTIFY\_CHANGE\_DIR\_NAME=2

\_FILE\_NOTIFY\_CHANGE\_FILE\_NAME=1

\_FILE\_NOTIFY\_CHANGE\_LAST\_WRITE=0x10

\_FILE\_NOTIFY\_CHANGE\_SECURITY=0x100

\_FILE\_NOTIFY\_CHANGE\_SIZE=0x8

\_FILE\_PERSISTENT\_ACLS=0x8

\_FILE\_SHARE\_DELETE=4

\_FILE\_SHARE\_READ=1

\_FILE\_SHARE\_WRITE=2

\_FILE\_TYPE\_CHAR=2

\_FILE\_TYPE\_DISK=1

\_FILE\_TYPE\_PIPE=3

\_FILE\_TYPE\_REMOTE=0x8000

\_FILE\_TYPE\_UNKNOWN=0x0

\_FILE\_UNICODE\_ON\_DISK=4

\_FILE\_VOLUME\_IS\_COMPRESSED=0x8000

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/file.md)

