[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# builtin.io 库模块帮助文�?
## ::Shell32 成员列表

### ::Shell32.?

可不用声明直接在此输入函数名并调用API函数

一、传入参数规则：

1、null参数不可省略

2�?2位整数类型，小于32位的整数、以及枚举类型都可以直接在API参数中写数值�?
3、对于任何数值类型的指针（输出参数）一律使用结构体表示，例如double \* v 表示为{ double v }

4、数组使用结构体表示

5、所有结构体传给API的都是指针地址，都是输出参数并增加返回�?
二、返回值规则：

1、返回值默认为int类型

2、可以使用\[API尾标\]改变返回值为其他类型

三、所有可用的【API尾标�?

::Shell32.ApiNameW() 切换到Unicode版本，字符串UTF8-UTF16双向转换

::Shell32.ApiNameA() 切换到ANSI版本,字符串不作任何转�?
::Shell32.ApiNameL() 返回值为64位LONG类型

::Shell32.ApiNameP() 返回值为指针类型

::Shell32.ApiNameD() 返回值为double浮点�?
::Shell32.ApiNameF() 返回值为float浮点�?
::Shell32.ApiNameB() 返回值为C++中的8位bool类型

注意【尾标】前必须是小写字�?
### ::Shell32.Control\_RunDLL(hwnd,hinst,cmdLine,cmdShow)

可用于启动控制面板命�?

hwnd可指定为0,hinst 可指定为 \_HINSTANSE,

cmdLine 指定启动参数,cmdShow 指定�?即可,

也可以通过process.rundll 运行此函�?

或通过 process.control 直接执行控制面板命令

### ::Shell32.SHChangeNotify(\_SHCNE,0,0,0)

通知操作系统外壳刷新,例如刷新桌面图标�?
参数依次为@eventId,@flags,@item1,@item2

参数@flags的值为5时函数名必须加上 W 尾标，即 ::Shell32.SHChangeNotifyW

### ::Shell32.ShellExecute(hwnd,operation,path,param,workDir,cmdShow)

执行 path 指定的程�?

第一个参数为数值格式的句柄,

最后一个参数为数�?指定�?即可,其他参数都是字符�?

详细用法请参考该 API 文档,

注意省略的参数也要指�?null �?

非声明式调用 API 不能减少参数个数,

raw.execute 函数提供类似功能，但所有参数都可以省略�?
process.execute 函数也提供类似功�?
### ::Shell32.api("字符串参�?,"void()" )

声明Kernel32 API函数

## io 成员列表

### io.appData

获取 %LocalAppData% 目录下的绝对路径�?
可选使用指定需要存入的数据

### io.appData(path,data)

将@path指定的相对路径转换为系统 %LocalAppData% 目录下的绝对路径,

可选使�?@data 指定需要存入的数据,

存入文件与目标文件长度不同或 PE 时间戳不同则允许替换旧文�?

指定 @data 参数后如果无法创建文件返回null,

最后返回转换所得的完整路径

### io.curDir

获取或修改当前目�?
### io.curDir()

无参数获取当前目�?
### io.curDir(dir)

�?@dir 参数指定的目录路径转换为完整路径并设为当前目�?
成功返回 true

### io.getSize()

获取参数@1指定路径的文件字节长�?

返回数�?
### io.getSpecial(\_CSIDL)

获取特殊文件�?

参数@1使用 \_CSIDL 开头的常量指定特殊文件夹的 CSIDL,

不指定参数@1则默认值为 \_CSIDL\_DESKTOP,

可选增加任意个拼接到目录后的子路径参数

这个函数与fsys.getSpecial函数用法接近,

但支持不定个数子路径参数, 不支持返回PIDL

fsys.knownFolder 可用于获取更多已知的特殊文件�?
### io.specialData(path,data,csidl)

�?@path 指定的相对路径转换为特殊文件夹下的绝对路�?

可选使�?@data 指定需要存入的数据,

存入文件与目标文件长度不同或 PE 时间戳不同则允许替换旧文�?

指定 @data 参数后如果无法创建文件返回null,

参数@csidl 使用 \_CSIDL 开头的常量指定特殊文件夹的 CSIDL,

不指定@csidl 则默认值为 \_CSIDL\_DESKTOP,

最后返回转换所得的完整路径

### io.tmpname

生成系统临时文件目录下的临时文件路径

### io.tmpname(prefix,ext)

生成临时文件路径�?
可选用 @prefix 参数指定前缀名，

可选用 @ext 参数指定后缀名，后缀名应包含�?
### io.updateData

更新指定文件的数�?
### io.updateData(data,path,...)

更新指定 @path 指定路径的文件为 @data 指定的数据�?
如果添加更多参数，则首先调用 io.joinpath 拼接�?@path 后面�?
存入文件与目标文件长度不同或 PE 时间戳不同则允许替换旧文件�?
替换失败返回 null，否则返回文件路�?
### 全局常量

### ::Shell32

默认已加载的Shell32.dll模块对象（参考标准库：peload.io），

提供Windows系统外壳 API

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/builtin/io.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/builtin/io.md')

