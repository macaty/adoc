[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# builtin.raw 库模块帮助文�?
## raw 成员列表

### raw.byte()

转换参数@1指定的数值为 byte 类型数值（8位整数）包装对象,

返回对象支持 tonumber tostring 等类型转换函数�?
用于调用非声明式原生 API 函数的参�?

默认传�?参数@2�?true 则用于传址参数（传数值的指针）�?
用于 COM 函数参数则总是传�? COM 函数也可使用 com.byte 函数

[返回对象:rawNumberObject](#rawNumberObject)

### raw.convertArray(源内存指�?源数组长�?"数据类型")

将指针指向的内存转换为普通数�?传入空指针返回空�?
数据类型参数可省�?默认�?pointer"

类型类型也可以直接传入一个声明元素类型的结构体参�?
注意该函数不会检测内存溢出错�?调用该函数时必须保证数组长度是正确的�?
### raw.double()

转换参数@1指定的数值为 double 类型数值（64位浮点数）包装对�?

返回对象支持 tonumber tostring 等类型转换函数�?
用于调用非声明式原生 API 函数的参�?

默认传�?参数@2�?true 则用于传址参数（传数值的指针）�?
用于 COM 函数参数则总是传�? COM 函数也可使用 com.double 函数

[返回对象:rawNumberObject](#rawNumberObject)

### raw.dup(源句�?源进�?目标进程,允许子进程继�?

返回复制的系统句�?
除参�?之外,其他参数可�?
默认仅在当前进程中复制句�?
复制的句柄应使用raw.closehandle释放

### raw.execute

运行外部程序，成功返�?true�?
process.execute 函数提供类似的功能，区别可参考函数源�?
### raw.execute(file,param,operation,showCmd,workDir,hwnd)

运行外部程序，成功返�?true�?
@file 指定要运行的程序路径，其他所有参数可省略�?
@param 字符串参数，可选指定启动参数�?
@operation 可选用一个字符串指定执行动词，省略则使用默认动词�?"open"�?
@showCmd 可选用 _SW_ 前缀常量指定显示选项，默认为 \_SW\_SHOW�?
@workDir 参数可选指定工作目录�?
@hwnd 可选指定所有窗口句柄，默认取当前线程活动窗�?
### raw.explore(path,args,...)

使用资源管理器（Explorer.exe）打开文件或目录�?
第一个参�?@path 指定文件路径，可为空值（ null ）�?
注意 Explorer.exe 不解析标准的命令行参数转义符，这一点与其他程序不同�?
如参�?@path 尾部有双反斜�?`\\` 则为无效路径并打开默认目录（打开我的文档，XP系统报错）�?
如参�?@path 指定�?","�?file:" 则打开“此电脑（This PC）”�?
如参�?@path 使用 `shell:::` 前缀则可以指定特殊路径的 CLSID�?
可用第二个参�?@args 或更多参数指�?Explorer.exe 命令行选项�?
例如指定 "/select" 在资源管理器选择指定路径�?
注意 "/n" 等选项在新系统中是无意义的，Explorer 将总是打开新窗口�?
### raw.float()

转换参数@1指定的数值为 float 类型数值（32位浮点数）包装对�?

返回对象支持 tonumber tostring 等类型转换函数�?
用于调用非声明式原生 API 函数的参�?

默认传�?参数@2�?true 则用于传址参数（传数值的指针）�?
用于 COM 函数参数则总是传�? COM 函数也可使用 com.float 函数

[返回对象:rawNumberObject](#rawNumberObject)

### raw.int()

转换参数@1指定的数值为 int 类型数值（32位整数）包装对象,

返回对象支持 tonumber tostring 等类型转换函数�?
用于调用非声明式原生 API 函数的参�?

默认传�?参数@2�?true 则用于传址参数（传数值的指针）�?
用于 COM 函数参数则总是传�? COM 函数也可使用 com.int 函数

[返回对象:rawNumberObject](#rawNumberObject)

### raw.join(buffer数组,分隔字符�?起始索引,结束索引)

拼接字符串或 buffer 数组，返�?buffer�?
如果拼接后长度为空，此函数返�?null�?
参数@1指定的数组可包含字符串或buffer�?
包含 buffer 的数组只能用 raw.join 拼接，不可使�?string.join 拼接

参数 @2 可选指定一个间隔字符串�?
起始索引与结束索引为可选参数，可传入负数表示自数组尾部倒计�?
### raw.long()

转换参数@1指定的数值为 long 类型数值（64位整数）包装对象,

返回对象支持 tonumber tostring 等类型转换函数�?
用于调用非声明式原生 API 函数的参�?

默认传�?参数@2�?true 则用于传址参数（传数值的指针）�?
用于 COM 函数参数则总是传�? COM 函数也可使用 com.long 函数

[返回对象:rawNumberObject](#rawNumberObject)

### raw.main

进程主模�?默认调用约定为stdcall

与raw.module("stdcall")返回的值相�?

可用于将当前进程中的函数指针转换为aardio函数

[返回对象:dllModuleObject](../raw/_.html#dllModuleObject)

### raw.mixin(指针,结构体对�?任意个混入对�?

混入新的�?支持任意个混入table对象,

自动更新指针指向内存,并返回结构体对象

### raw.module("调用约定")

指定约定并返回进程主模块,

省略参数时调用约定默认为stdcall,

可用于将当前进程中的函数指针转换为aardio函数,

### raw.module()

[返回对象:dllModuleObject](../raw/_.html#dllModuleObject)

### raw.serializeDupHandle("类名",句柄)

复制进程内有效句柄并序列化对�?
只能用于\_serialize元方法，且必须kernelCall参数为真

序列化类构造函数必须支持指针参�?为指针类型句�?参数2为true的参�?
并负责在析构函数中调�?raw.closehandle 释放该句�?
### raw.typeOfArray()

如果参数是一个包含原生数组的结构体，

返回原生类型名，以及数组字段名字�?
如果是其他对象则返回 null �?
### raw.ubyte()

转换参数@1指定的数值为 BYTE 类型数值（8位无符号整数）包装对�?

返回对象支持 tonumber tostring 等类型转换函数�?
用于调用非声明式原生 API 函数的参�?

默认传�?参数@2�?true 则用于传址参数（传数值的指针）�?
用于 COM 函数参数则总是传�? COM 函数也可使用 com.ubyte 函数,

注意在原生类型中使用大写�?BYTE 类型表示8位无符号整数

[返回对象:rawNumberObject](#rawNumberObject)

### raw.uint()

转换参数@1指定的数值为 INT 类型数值（32位无符号整数）包装对�?

返回对象支持 tonumber tostring 等类型转换函数�?
用于调用非声明式原生 API 函数的参�?

默认传�?参数@2�?true 则用于传址参数（传数值的指针）�?
用于 COM 函数参数则总是传�? COM 函数也可使用 com.uint 函数,

注意在原生类型中使用大写�?INT 类型表示32位无符号整数

[返回对象:rawNumberObject](#rawNumberObject)

### raw.ulong()

参数@1可传入数值或 math.size64 对象,

返回适用�?LONG 类型数值（64位无符号整数）的包装对象,

返回对象支持 tonumber tostring 等类型转换函数�?
用于调用非声明式原生 API 函数的参�?

默认传�?参数@2�?true 则用于传址参数（传数值的指针）�?
用于 COM 函数参数则总是传�? COM 函数也可使用 com.ulong 函数,

注意在原生类型中使用大写�?LONG 类型表示64位无符号整数

[返回对象:rawNumberObject](#rawNumberObject)

### raw.uword()

转换参数@1指定的数值为 WORD 类型数值（16位无符号整数）包装对�?

返回对象支持 tonumber tostring 等类型转换函数�?
用于调用非声明式原生 API 函数的参�?

默认传�?参数@2�?true 则用于传址参数（传数值的指针）�?
用于 COM 函数参数则总是传�? COM 函数也可使用 com.uword 函数,

注意在原生类型中使用大写�?WORD 类型表示16位无符号整数

[返回对象:rawNumberObject](#rawNumberObject)

### raw.word()

转换参数@1指定的数值为 word 类型数值（16位整数）包装对象,

返回对象支持 tonumber tostring 等类型转换函数�?
用于调用非声明式原生 API 函数的参�?

默认传�?参数@2�?true 则用于传址参数（传数值的指针）�?
用于 COM 函数参数则总是传�? COM 函数也可使用 com.word 函数

[返回对象:rawNumberObject](#rawNumberObject)

## rawNumberObject 成员列表

### rawNumberObject.value

对象存储的数�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/builtin/raw.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/builtin/raw.md')

