[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# dotNet.appDomain 库模块帮助文�?
## dotNet 成员列表

### dotNet.appDomain

创建应用程序�?

注意应当通过导入 dotNet 库自动导�?dotNet.appDomain

### dotNet.appDomain()

不指定参数为当前线程创建唯一的应用程序域实例,

该实例可能被其他代码使用,主动调用 unload 函数会被忽略,

线程结束前会自动释放此实例�?
成功返回应用程序�?失败返回 null,错误信息,

失败一般是因为系统没有安装 .NET 运行时�?
除了XP系统，WIN7 以及 WIN7 以上系统已自�?.NET 运行�?

所以不检测返回值也行�?
注意应当通过导入 dotNet 库自动导�?dotNet.appDomain

[返回对象:dotNetAppDomainObject](#dotNetAppDomainObject)

### dotNet.appDomain(clr,domainName)

参数 @clr 指定 dotNet.clr 对象�?
可选用 @domainName 指定应用程序域名称，

指定参数时应改用 dotNet.clr 对象�?createAppDomain 函数

无参数调�?dotNet.appDomain 总是返回默认单例应用程序域，

引入 dotNet 库也会自动创建默认应用程序域

## NetDictionaryObject 成员列表

### NetDictionaryObject.Add(key,value)

添加键�?
### NetDictionaryObject.Clear()

清空字典

### NetDictionaryObject.ContainsKey(key)

是否包含参数 @key 指定键的�?
### NetDictionaryObject.ContainsValue(value)

是否包含参数 @value 指定值的�?
### NetDictionaryObject.Count

包含键值对总数

### NetDictionaryObject.Remove(key)

移除参数 @key 指定的键�?
## dotNetAppDomainObject 成员列表

### dotNetAppDomainObject.Array

```aardio aardio
System.Array

```

### dotNetAppDomainObject.Drawing

```aardio aardio
System.Drawing

```

### dotNetAppDomainObject.appDomainReal

AppDomain 托管对象

### dotNetAppDomainObject.buffer(初始�?

分配可读写的、固定长度的字节数组�?
参数可以是一个结构体、字符串、或 buffer,传入{ }返回null,

重新分配内存并复制初始值指定的数据�?
返回封包 buffer �?dotNet.object 对象

### dotNetAppDomainObject.buffer(长度,初始�?

分配可读写的、固定长度的字节数组�?
参数一指定需要分配的内存大小,

,内存初始值可以用结构体、指针、buffer、或字符串指定一段内存数�?

也可用一个数值指定所有字节的初始�?不指定默认初始化所有字节为0,

如果初始值指定为字符串或buffer类型�?
填充初始数据以后剩余的字节会全部初始为为0

返回封包 buffer �?dotNet.object 对象

### dotNetAppDomainObject.byte

创建 .NET System.SByte 类型数值或数组

### dotNetAppDomainObject.byte(value,byRef)

创建 .NET System.SByte 类型数值或数组�?
用于存储8位整数�?
参数 @value 可以为数值或数组�?
参数 @byRef �?true 则支�?.NET 的输出或引用参数

### dotNetAppDomainObject.clr

.NET 运行�?
[返回对象:dotNetClrObject](#dotNetClrObject)

### dotNetAppDomainObject.createArray

创建 .NET 类型化数组�?
.NET 通常要求数组类型完全匹配，可以用这个函数创建类型匹配的数组�?
包含.NET 对象的普�?aardio 数组在传�?.NET 时也会临时转换为类型化数�?
默认的普通数值数组传�?.NET �?double 数组，但支持自适应转换类型�?
也可以用 dotNet.double,dotNet.int 等函数创建类型化数值数组�?
注意 .NET 数组对象应当�?Length 属性取数组长度而非�?#号取长度�?
.NET 中的简单值类型数组在 aardio 中会转换�?com.SafeArray 数组�?
com.SafeArray 数组可以�?# 取长�?
### dotNetAppDomainObject.createArray(数组)

参数 @1 请指定数组�?
包含.NET 对象的普通数组返回为 .NET 类型化数组，

传入其他任何类型参数直接返回

### dotNetAppDomainObject.createArray(类型,长度...)

参数 @1 请指�?.NET 类型�?
类型通常�?dotNet.import 导入，或�?.NET 对象�?GetType 函数获取�?
至少指定一个数组长度参数，可指定多个长度参数以创建多维数组

### dotNetAppDomainObject.createArrayList()

[返回对象:dotNetCrlArrayListObject](#dotNetCrlArrayListObject)

### dotNetAppDomainObject.createArrayList(初始化数�?

创建 System.Collections.ArrayList 对象

可传递到C#函数�?C#中应声明�?object 类型,然后强制转换�?ArrayList,

可选参数一指定 table 数组用于初始化对�?
### dotNetAppDomainObject.createCompiler("C\#")

创建C#编译�?
### dotNetAppDomainObject.createCompiler("VB")

创建VB编译�?
### dotNetAppDomainObject.createCompiler()

[返回对象:dotNetCompilerObject](#dotNetCompilerObject)

### dotNetAppDomainObject.createInstance(程序�?"类名",其他调用参数)

参数一可以是程序集对象,名称或路径都可以,

调用类的构造函�?支持传入多个调用参数并返回创建的对象�?
失败返回空�?以及错误信息

### dotNetAppDomainObject.createNameValueList(names,values)

创建 List\> 列表对象,

参数@name,@value 必须是长度相等的非空数组,

返回 List 对象的每个元素都具有 Name,Value 属性，

其值由 @names,@values 参数按数组索引顺序分�?
### dotNetAppDomainObject.createWebService

创建 Web 服务程序�?
### dotNetAppDomainObject.createWebService()

[返回对象:dotNetCrlAssemblyObject](#dotNetCrlAssemblyObject)

### dotNetAppDomainObject.createWebService(服务网址,名字空间,协议�?DLL路径)

创建 Web 服务程序�?可选在参数@2中指定一个自定义的名字空�?
协议名默认为"Soap",可选�?Soap12",

如果使用参数@4指定输出DLL路径则在内存中编译程序集

### dotNetAppDomainObject.delegate

用于操作 .NET 委托（Delegate）或事件（event），

�?.NET 里函数要转换为委托对象才能作为回调函数传输，

�?aardio 里对所�?.NET 对象的委托字段直接赋值总是覆盖而不是追加，

对所�?.NET 事件赋值时总是追加而不是覆盖，

[返回对象:dotNetDelegateObject](#dotNetDelegateObject)

### dotNetAppDomainObject.dict

将非空表转换�?.NET 字典�?
如果要创建空字典，调用返回对象的 Clear 函数清空即可�?
返回对象支持用下标操作符访问键值对�?
可用 dotNet.each 遍历字典�?
### dotNetAppDomainObject.dict()

[返回对象:NetDictionaryObject](#NetDictionaryObject)

### dotNetAppDomainObject.dict(tab,byRef)

将非空表转换�?.NET 字典（Dictionary）对象�?
如果传入空表�?null 返回 null 值�?
否则必须传入非空表，表中所有的键必须是相同类型�?
表中所有的值必须是相同类型�?
参数 @byRef 为可选参数，如果 @byRef �?true�?
则返回对象可作为 .NET 输出与引用参数使�?
### dotNetAppDomainObject.double

创建 .NET System.Double 类型数值或数组

### dotNetAppDomainObject.double(value,byRef)

创建 .NET System.Double 类型数值或数组�?
用于存储64位浮点数�?
参数 @value 可以为数值或数组�?
参数 @byRef �?true 则支�?.NET 的输出或引用参数,

注意普通数值传�?.NET 函数时，

整数默认转为32位整�?小数默认按double类型处理

### dotNetAppDomainObject.each(netObj)

```aardio aardio
for i,v in dotNetAppDomainObject.each(/*输入需要遍历的 .NET 对象或普通数组，
返回�?i 为当前索�?v 为当前值，
注意并非所�?.NET 类型都支持此接口*/) {

}

```

### dotNetAppDomainObject.float

创建 .NET System.Single 类型数值或数组

### dotNetAppDomainObject.float(value,byRef)

创建 .NET System.Single 类型数值或数组�?
用于存储32位浮点数�?
参数 @value 可以为数值或数组�?
参数 @byRef �?true 则支�?.NET 的输出或引用参数

### dotNetAppDomainObject.getInstanceMember(目标对象,"字段�?)

获取对象字段或属�?
失败返回空�?以及错误信息

### dotNetAppDomainObject.getStaticMember(程序�?"类型�?字段�?)

参数一可以是程序集对象,名称或路径都可以,

获取静态字段、属性值、枚举值等�?
### dotNetAppDomainObject.id

应用程序�?ID\

### dotNetAppDomainObject.import

加载程序集，导入 .NET 名字空间、类、枚举�?
在当前应用程序域 import,load 等函数不会导入重复的程序集，

同一程序集中不会重复导入相同的名字空间�?
如果已存在同名的全局名字空间但元表为空（并未导入 .NET 名字空间），

则导�?.NET 名字空间到已存在的名字空间�?
如果已存在同名的全局名字空间但元表非空（通常为已导入�?.NET 名字空间 ），

则不会覆盖已存在的名字间，而是在返回值返回当前调用实际创建的名字空间�?
加载程序集或依赖程序集失败时此函数会抛出异常�?
### dotNetAppDomainObject.import()

[返回对象:dotNetNameSpaceObject](appDomain.html#dotNetNameSpaceObject)

### dotNetAppDomainObject.import(名字空间)

加载参数 @1 指定文件名的程序集，并导入同名的 .NET 名字空间或类�?
当程序集文件名与导入名字相同时，可以省略 指定程序集名称的参数 @2�?
返回名字空间可作为类构造函数调用并创建对象�?
也可以用成员操作符获取静态成员，或调用静态函数�?
导入�?.NET 名字空间在正常访问其成员时会触发元方法以获取并创建下级名字空间、类、枚举等�?
但导入名字空间的函数（以�?namespace 语句）创建的上级名字空间并不会主动导入同�?.NET 名字空间\\�?
此函数会尽可能重用已存在�?aardio 全局名字空间导入 .NET 名字空间�?
如果该全局名字空间已导入其�?.NET 名字空间则不会覆盖已存在的名空间�?
此函数总是会返回当前调用实际创建的名字空间�?
### dotNetAppDomainObject.import(名字空间,程序集名)

加载参数@2指定文件名字的程序集�?
�?参数@1 指定的空间、类、枚举等导入 aardio 全局名字空间�?
必须指定完整名字空间�?
参数 @1 可指定名字空间也可以指定要导入的名字空间数组�?
在当前应用程序域 import,load 等函数不会导入重复的程序集，

同一程序集中不会重复导入相同的名字空间�?
返回名字空间可作为类构造函数调用并创建对象�?
也可以用成员操作符返回静态成员，或调用静态函数�?
导入�?.NET 名字空间在正常访问其成员时会触发元方法以获取并创建下级名字空间、类、枚举等�?
但导入名字空间的函数（以�?namespace 语句）创建的上级名字空间并不会主动导入同�?.NET 名字空间�?
此函数会尽可能重用已存在�?aardio 全局名字空间导入 .NET 名字空间�?
如果该全局名字空间已导入其�?.NET 名字空间则不会覆盖已存在的名空间�?
此函数总是会返回当前调用实际创建的名字空间

### dotNetAppDomainObject.int

创建 .NET System.Int32 类型数值或数组

### dotNetAppDomainObject.int(value,byRef)

创建 .NET System.Int32 类型数值或数组�?
用于存储32位整数�?
参数 @value 可以为数值或数组�?
参数 @byRef �?true 则支�?.NET 的输出或引用参数,

注意普通数值传�?.NET 函数时，

整数默认转为32位整�?小数默认按double类型处理

### dotNetAppDomainObject.interop

aardio.Interop.dll 程序�?
[返回对象:dotNetCrlAssemblyObject](#dotNetCrlAssemblyObject)

### dotNetAppDomainObject.invokeInstanceMember(目标对象,"方法�?,其他调用参数)

调用类的成员方法,支持传入多个调用参数并返回�?
失败返回空�?以及错误信息

### dotNetAppDomainObject.invokeMember(程序�?"类名","方法�?,BindingFlags,目标对象,其他调用参数)

调用类方�?目标对象可省�?

失败返回空�?以及错误信息

### dotNetAppDomainObject.invokeStaticMember(程序�?"类型�?方法�?,其他调用参数)

参数一可以是程序集对象,名称或路径都可以,

调用类的静态方�?支持传入多个调用参数并返回值�?
失败返回空�?以及错误信息

### dotNetAppDomainObject.load

使用当前线程默认应用程序域载入并返回程序集（DLL）�?
在当前应用程序域如果已使用此函数导入同名程序集，

则直接返回该程序�?
### dotNetAppDomainObject.load("程序集名")

使用当前线程默认应用程序域载入并返回程序集�?
参数可以是程序集（DLL）名称或路径�?
此函数会按以下顺序调�?.NET 函数尝试加载程序集：

└── Assembly.LoadWithPartialName

└── Assembly.Load

└── Assembly.LoadFrom

└── Assembly.LoadFile

### dotNetAppDomainObject.load("程序集名",虚拟程序集数据或路径)

首先在『虚拟程序集引用表』中注册程序集名�?
参数 @2 指定对应的内�?DLL 数据�?DLL 路径（支�?EXE 内嵌资源）�?
然后再调�?load 函数加载并返回该虚拟程序�?
### dotNetAppDomainObject.load()

[返回对象:dotNetCrlAssemblyObject](#dotNetCrlAssemblyObject)

### dotNetAppDomainObject.loadAppData

可用于嵌入并�?%appData% 目录加载

不支持通过 loadFile 函数内存加载的程序集

### dotNetAppDomainObject.loadAppData()

[返回对象:dotNetCrlAssemblyObject](#dotNetCrlAssemblyObject)

### dotNetAppDomainObject.loadAppData(path,data)

�?@path 指定 %appData% 目录下的相对路径,

�?@data 参数指定的内存程序集数据释放到该路径,

并使�?load 函数加载此程序集,

@data 参数应在路径前加$符号使文件数据嵌入到代码�?
### dotNetAppDomainObject.loadFile

使用当前线程默认应用程序域载入程序集（DLL）�?
参数可以�?DLL 路径，内�?DLL，或 EXE 内嵌资源�?
此函数并不支�?『虚拟程序集引用表』，无法在内存添加依�?DLL

程序集如果引用了自身路径必须改用 load 函数加载

### dotNetAppDomainObject.loadFile("程序集路�?)

使用当前线程默认应用程序域载入程序集,

参数可以�?DLL 路径，内�?DLL，或 EXE 内嵌资源�?
在路径字符串前加$符号可将文件编译并嵌�?aardio 代码,

可选在�?个参数中指定pdb调试数据或pdb调试文件路径

### dotNetAppDomainObject.loadFile()

[返回对象:dotNetCrlAssemblyObject](#dotNetCrlAssemblyObject)

### dotNetAppDomainObject.long

创建 .NET System.Int64 类型数值或数组

### dotNetAppDomainObject.long(value,byRef)

创建 .NET System.Int64 类型数值或数组�?
用于存储64位整数�?
参数 @value 可以为数值或数组�?
参数 @byRef �?true 则支�?.NET 的输出或引用参数

### dotNetAppDomainObject.object

转换参数 @1 指定�?aardio 值或数组�?.NET 原生 DispatchableObject 对象�?
并返回为 aardio 可操作的 dotNet.object 对象�?
也可用于转换 原生 .NET 对象�?dotNet.object �?
或转�?dotNet.object 为支持引�?dotNet.object�?
dotNet.object 如果存储的是 Primitive,enum,string 类型或这些类型的数组�?
则可以使�?Value 属性读写值�?
dotnet.object 对象支持�?tostring 转换为字符串�?
如果存储的是数值则支持调用 tonumber 函数转为普通数值�?
### dotNetAppDomainObject.object(value,byRef)

参数 @byRef �?true 则支�?.NET 的输出或引用参数

参数 @value 如果指定�?aardio 对象或数组�?
则转换为 .NET 原生 DispatchableObject 对象，并封装�?dotNet.object 后返回�?
如果参数 @1 指定 dotNet.object 对象且参�?@2 不为 true 则直接返回�?
如果参数传入原生 .NET 对象且参�?@2 不为 true 则仅转换�?dotNet.object�?
如果参数 @2 �?true，则这些对象都会转换�?DispatchableObject 并返回新�?dotNet.object

### dotNetAppDomainObject.reference

在『虚拟程序集引用表』注册一个或多个虚拟程序集，

这些虚拟程序集可以是内存程序集、本地程序集、EXE 内嵌资源中的程序集�?
aardio 加载�?.NET 程序找不到程序集（DLL）时�?
会查找『虚拟程序集引用表』并加载已注册的虚拟 DLL

### dotNetAppDomainObject.reference(assemblyName2pathOrData)

在『虚拟程序集引用表』注册多个虚拟程序集（DLL）�?
@assemblyName2pathOrData 指定一个表�?
表的「键」为虚拟程序集短名称�?DLL 文件�?），

键对应的「值」指定程序集内存数据或程序集路径（支持内嵌资源）

### dotNetAppDomainObject.reference(simpleAssemblyName,pathOrData)

在『虚拟程序集引用表』注册虚拟程序集（DLL）�?
@simpleAssemblyName 指定程序集短名称（虚�?DLL 文件名）

@pathOrData 指定程序集路径或内存数据，支持内嵌资源路�?
@pathOrData 也可以是返回程序集路径或数据的回调函�?
### dotNetAppDomainObject.setInstanceMember(目标对象,"字段�?,�?

设置对象实例的字段或属�?
成功返回 true ,失败返回空�?以及错误信息

### dotNetAppDomainObject.ubyte

创建 .NET System.Byte 类型数值或数组

### dotNetAppDomainObject.ubyte(value,byRef)

创建 .NET System.Byte 类型数值或数组�?
用于存储8位无符号整数�?
参数 @value 可以为数值或数组�?
参数 @byRef �?true 则支�?.NET 的输出或引用参数

### dotNetAppDomainObject.uint

创建 .NET System.UInt32 类型数值或数组

### dotNetAppDomainObject.uint(value,byRef)

创建 .NET System.UInt32 类型数值或数组�?
用于存储32位无符号整数�?
参数 @value 可以为数值或数组�?
参数 @byRef �?true 则支�?.NET 的输出或引用参数

### dotNetAppDomainObject.ulong

创建 .NET System.UInt64 类型数值或数组

### dotNetAppDomainObject.ulong(value,byRef)

创建 .NET System.UInt64 类型数值或数组�?
用于存储64位无符号整数�?
参数 @value 可以为数值或数组�?
参数 @byRef �?true 则支�?.NET 的输出或引用参数

### dotNetAppDomainObject.unload()

卸载应用程序�?一般不需要手动调用此函数,

当前线程退出时会自动释放此线程创建的所有应用程序域,

不带参数调用 dotNet.appDomain 创建的应用程序域不应手动调用此函数释�?
### dotNetAppDomainObject.utility

aardio.Interop.Utility 对象

### dotNetAppDomainObject.uword

创建 .NET System.UInt16 类型数值或数组

### dotNetAppDomainObject.uword(value,byRef)

创建 .NET System.UInt16 类型数值或数组�?
用于存储16位无符号整数�?
参数 @value 可以为数值或数组�?
参数 @byRef �?true 则支�?.NET 的输出或引用参数

### dotNetAppDomainObject.word

创建 .NET System.Int16 类型数值或数组

### dotNetAppDomainObject.word(value,byRef)

创建 .NET System.Int16 类型数值或数组�?
用于存储16位整数�?
参数 @value 可以为数值或数组�?
参数 @byRef �?true 则支�?.NET 的输出或引用参数

### dotNetAppDomainObject.wrapObject()

如参数是原生 .NET 对象,则返�?dotNet.object 对象，否则直接返回参数�?
所�?.NET 原生对象已经自动转换�?dotNet.object 对象�?
除非 .NET 调用普�?aardio 对象的成员函数而非回调特定的委托或事件函数�?
这时候回调参数中�?.NET 对象需要用此函数转换，但数值和字符串不需要转换�?
参数传入 com.IsNetObject 函数会返回非 0 值即为原�?.NET 对象�?
非原�?.NET 对象转换�?dotNet.object 应当直接调用 dotNet.object 函数�?
## dotNetCompilerObject 成员列表

### dotNetCompilerObject.Compile

编译并返回程序集

### dotNetCompilerObject.Compile()

[返回对象:dotNetCrlAssemblyObject](#dotNetCrlAssemblyObject)

### dotNetCompilerObject.Compile(outpath)

编译并返回程序集,所有参数可�?

如果参数 @outpath 指定了输�?dll �?exe 文件路径，则输出为文�?

遇到错误不会抛出异常，请调用 getLastError 函数获取错误信息

### dotNetCompilerObject.CompileOrFail

编译并返回程序集

### dotNetCompilerObject.CompileOrFail()

[返回对象:dotNetCrlAssemblyObject](#dotNetCrlAssemblyObject)

### dotNetCompilerObject.CompileOrFail(outpath)

编译并返回程序集,所有参数可�?

如果参数 @outpath 指定了输�?dll �?exe 文件路径，则输出为文�?

遇到错误会抛出异�?
### dotNetCompilerObject.Reference

引用程序集，System.dll 已默认添�?
注意这函数不支持内存 DLL�?
也不支持�?dotNet.reference 添加的内�?DLL�?
### dotNetCompilerObject.Reference(assemblyDir,subPath...)

引用程序�?

参数@1指定目录,可指定一个或多个子路�?

使用 io.joinpath 函数合并参数转换为完整路�?

然后引用该程序集�?
### dotNetCompilerObject.Reference(assemblyPath,...)

引用程序�?

可指定任意多个程序集路径或名称参�?

如果指定不含 dll 后缀名的程序集名，则加载程序集并转换为完整路径�?
### dotNetCompilerObject.Source

```aardio aardio
dotNetCompilerObject.Source = /***
using System;

namespace CSharpLibrary
{
    public class NetObject
    {
        public NetObject()
        {
            /*Source 属性可用字符串或字符串数组指定要编辑的代码�?如果指定字符串则启用 aardio 模板语法，如果代码开始没有模板标记则自动添加�?编译器对象的 ownerArgs 属性指定模�?owner 参数�?CLR v2.0 / v4.0 可运行在 3.x,4.x 编译�?DLL，但编译器仅支持 CLR 相同版本语法�?如果要添加文件，请改�?addSource 函数�?/
        }
    }
}
***/

```

### dotNetCompilerObject.addSource

添加源码，使用此函数添加源码�?Source 属性将变为数组

### dotNetCompilerObject.addSource(code,rep)

参数 @code 可以指定代码或代码文件路径�?
可指定嵌入资源路径，源文件必须使�?UTF-8 编码�?
如果代码开始的非空白空字为 <? �??\> 则启�?aardio 模板语法�?
编译器对象的 ownerArgs 属性指定模�?owner 参数�?
参数 @rep 指定是否丢弃之前添加的代�?
### dotNetCompilerObject.defaultSource

编译前默认添加到前面的代�?
### dotNetCompilerObject.getLastError()

获取编译错误信息

### dotNetCompilerObject.getProvider()

编译�?
### dotNetCompilerObject.import

编译代码生成程序集，遇到错误会抛出异常�?
�?参数@1指定的名字空间或类导�?aardio 全局名字空间�?
在同一程序集中不会重复导入名字空间�?
如果程序集用不是�?load 函数加载，则有可能重复导入名字空�?

重复导入 .NET 名字空间不会修改已存在的全局名字空间�?
但此函数总是会返回当前调用实际创建的名字空间

### dotNetCompilerObject.import()

[返回对象:dotNetNameSpaceObject](appDomain.html#dotNetNameSpaceObject)

### dotNetCompilerObject.import(netNamespace)

编译代码生成程序集，遇到错误会抛出异常�?
�?参数@1指定的名字空间或类导�?aardio 全局名字空间�?
必须指定完整名字空间,不传入参数则默认指定参数为程序集名称�?
返回名字空间可作为类构造函数调用并创建对象

也可以用成员操作符返回静态成员，或调用静态函数�?
重复导入 .NET 名字空间不会修改已存在的全局名字空间�?
但此函数总是会返回当前调用实际创建的名字空间

### dotNetCompilerObject.loadcode

用于自定义板解析函数�?
用于解析启用 aardio 模板语法�?C# 代码�?
默认指向 string.loadcode �?
### dotNetCompilerObject.ownerArgs

模板语法使用�?owner 参数，默认为表对象�?
## dotNetCompilerObject.Parameters 成员列表

编译参数

### dotNetCompilerObject.Parameters.CompilerOptions

```aardio aardio
dotNetCompilerObject.Parameters.CompilerOptions = "/optimize /unsafe"/*编译参数�?optimize 为开启优�?/

```

### dotNetCompilerObject.Parameters.GenerateExecutable

是否编译为EXE执行文件

编译为DLL设为false

### dotNetCompilerObject.Parameters.GenerateInMemory

是否内存编译

### dotNetCompilerObject.Parameters.OutputAssembly

指定输出文件路径,

参数需要调用io.fullpath()转换为绝对路�?

需要设GenerateInMemory为false取消内存编译,

调用setGenerateExecutable指定编译为DLL或者EXE

## dotNetCrlArrayListObject 成员列表

### dotNetCrlArrayListObject.Add(添加对象)

添加成员到数组中

### dotNetCrlArrayListObject.Clear()

添空数组

### dotNetCrlArrayListObject.ToArray()

转换并返回数�?
### dotNetCrlArrayListObject.ToList()

转换并返�?List 对象

## dotNetCrlAssemblyObject 成员列表

### dotNetCrlAssemblyObject.FullName

获取程序集的全名

### dotNetCrlAssemblyObject.Location

获取完整路径

### dotNetCrlAssemblyObject.appDomain

加载此程序集的应用程序域

[返回对象:dotNetAppDomainObject](#dotNetAppDomainObject)

### dotNetCrlAssemblyObject.getStaticMember("类名.字段�?)

获取字段或属性值、或枚举�?
### dotNetCrlAssemblyObject.import

�?.NET 类名或名字空间导�?aardio 全局名字空间�?
在当前应用程序域 import,load 等函数不会导入重复的程序集，

在同一程序集中不会重复导入名字空间�?
如果程序集用其他函数加载，则有可能重复导入名字空�?

重复导入 .NET 名字空间不会修改已存在的全局名字空间�?
但此函数总是会返回当前调用实际创建的名字空间

### dotNetCrlAssemblyObject.import(netNamespace)

将参数@1 指定�?.NET 类名或名字空间导�?aardio 全局名字空间�?
必须指定完整名字空间�?
参数 @1 可指定名字空间也可以指定要导入的名字空间数组�?
不传入参数则默认指定参数为程序集名称�?
返回名字空间可作为类构造函数调用并创建对象

也可以用成员操作符返回静态成员，或调用静态函数�?
重复导入 .NET 名字空间不会修改已存在的全局名字空间�?
但此函数总是会返回当前调用实际创建的名字空间

### dotNetCrlAssemblyObject.import(netNamespace,...)

参数@1 指定要导入的 .NET 类名�?
如果再指定一个或多个类型参数时则导入泛型类�?
类型参数可以是导入的 .NET 类、类名全称、System.Type.GetType 获取的类型对象�?
对导入的 .NET 类使用下�?\["<>"\] 也可以返回一个创建泛型类的函数�?
泛型类不会缓存，也不会设�?aardio 全局名字空间

### dotNetCrlAssemblyObject.invokeStaticMember("类名.方法�?,... )

调用类的静态方�?

可添加不定个数调用参�?
失败返回空�?以及错误信息

### dotNetCrlAssemblyObject.new("类名",... )

创建对象实例,

可添加不定个数构造参�?
失败返回空�?以及错误信息

## dotNetDelegateObject 成员列表

### dotNetDelegateObject.combine

合并委托

�?.NET 里函数要转换为委托对象才能作为回调函数传�?
### dotNetDelegateObject.combine(委托对象1,委托对象2)

返回合并的委托对�?允许省略所有参数，

如果指定参数则至少有一�?.NET 委托对象�?
另一个参数可以是委托对象，也可指定普�?aardio 函数或表,

如果是普�?aardio 表则回调 \_call 元方�?

aardio 函数或表参数会自动转换为所需类型�?.NET 委托

### dotNetDelegateObject.combine(对象,委托成员�?委托对象)

自参数@1指定�?.NET 对象中查询参�?@2指定的的属性或字段,

如果该成员是一�?delegate �?event 类型，则合并参数@2，@3指定的委托并更新该成员的值�?
原委托成员可为空值，但参数@1,@2 不可省略�?
参数 @3 可指�?.NET 委托对象、null 值或省略�?
如果参数 @3 是普通的 aardio 函数或表则转换为所需类型�?.NET 委托�?
此函数返回参数@3创建的委托对�?可用�?remove 函数.

### dotNetDelegateObject.create

创建委托

�?.NET 里函数要转换为委托对象才能作为回调函数传�?
### dotNetDelegateObject.create(对象,委托成员�?函数对象)

自参数@1指定�?.NET 对象中查询参�?@2指定的的属性或字段,

如果该成员是一�?delegate �?event 类型�?
则将@3指定的函数转换为该类型的委托对象并返�?
### dotNetDelegateObject.list()

返回参数 @1 指定委托对象的调用对象列�?

相当于调用委托对象的 GetInvocationList 函数�?
### dotNetDelegateObject.remove

移除委托

### dotNetDelegateObject.remove(委托对象1,委托对象2)

自参数@1指定的委托中移除以参数@2指定的委托，

所有参数必须是 .NET 委托对象,

成功返回新的委托�?
失败或委托调用链没有变化返回 null,

任何一个参数为 null 返回 null

### dotNetDelegateObject.remove(对象,委托成员�?委托对象)

自参数@1指定�?.NET 对象中查询参�?@2指定的的属性或字段,

如果该成员是一�?delegate �?event 类型，则移除参数@3指定的委托并更新该成员的值�?
原委托成员可为空值，但参数@1,@2 不可省略�?
参数 @3 指定需要移除的 .NET 委托对象�?
不指定参�?@3 则不执行任何操作�?
移除成功返回 true，失败返�?false

## dotNetNameSpaceObject 成员列表

### dotNetNameSpaceObject.?

.NET 名字空间、类、结构体的成员，

可访问成员名字空间、类、枚举、静态属性或字段�?
导入的类可用于构�?.NET 对象，传�?.NET 则自动转为该类的 Type 对象�?
通过下标 \["<>"\] 可返回一个创建泛型类的函数，函数参数为类型对象或完整类型名称�?
[返回对象:dotNetNameSpaceObject](appDomain.html#dotNetNameSpaceObject)

### dotNetNameSpaceObject.assembly

导入�?.NET 名字空间的程序集对象�?
[返回对象:dotNetCrlAssemblyObject](#dotNetCrlAssemblyObject)

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/dotNet/appDomain.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/dotNet/appDomain.md')

