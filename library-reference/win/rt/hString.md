[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.rt.hString 库模块帮助文�?
## win.rt 成员列表

### win.rt.hString

WinRT 字符�?

仅支�?Win10 以及 Win10 以上版本

创建 WinRT 字符�?

返回值可作为 tostring 参数转换�?aardio 字符�?

可用于调�?WinRT 函数�?HSTRING 类型句柄参数

也可以作为左操作数使�?\+ �?\+\+ 操作�?
与其他值拼接返回新�?win.rt.hString 对象

### win.rt.hString()

创建空的 WinRT 字符�?
[返回对象:winRtHStringObject](#winRtHStringObject)

### win.rt.hString(HSTRING)

传入 HSTRING 指针,

复制此指针并返回新的 WinRT 字符串对�?

此类型参数构建的对象需要调�?free 函数释放

### win.rt.hString(value)

传入任何�?null,pointer 类型�?

此函数自动调�?tostring 转换为字符串参数,

然后再创建并返回 WinRT 字符�?

如果传入�?null 值，则应尽早调用 free 函数释放字符�?
### win.rt.is()

判断输入值是�?win.rt.hString 对象

## winRtHStringObject. 成员列表

### winRtHStringObject..byStruct()

生成一个结构体,

用于�?API 中接�?HSTRING 类型的输出参�?

�?C++ 中该输出参数类型应为 HSTRING \*,

�?aardio 中对应参数可声明�?struct &

或者免声明调用 API 并传�?byStruct 的返回值作为参�?
当返回的结构体获取到 HSTRING 句柄�?

会立即更新调�?byStruct 成员函数�?win.rt.hString 对象,

在此之前会自动调�?free 函数释放之前可能需要释放的 HSTRING

通过 byStruct 获取到的 HSTING 未增加引用计数也不需要释�?

应立即通过 tostring 转换�?aardio 字符串或通过copy复制,

并调�?free 函数清空或直接弃用或置为 null �?
### winRtHStringObject..copy()

复制并返回新的字符串,

复制的字符串应调�?free 函数释放

### winRtHStringObject..free()

释放字符�?

即使不调�?回收该变量时也会自动调用此函�?

如果调用 win.rt.hString 传入了非 null 参数则应尽早调用此函�?

或者通过拼接、调�?copy 函数等创建新�?WinRT 字符串都应当调用此函数释�?

否则不必要调用此函数

### winRtHStringObject..size()

字符串长�?按字符计�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/rt/hString.md)

