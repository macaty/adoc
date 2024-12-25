[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# raw �?- 声明原生 API 函数

使用 raw 库函数可操作 [原生数据类型](datatype.html)、可导入外部 DLL 文件提供的原�?API 函数�?
## 一、加�?dll 模块 [\#](\#loadDll)

语法�?
`dll = raw.loadDll( path | strMemoryDll,shareName,callingConvention="stdcall");`

说明�?
raw.loadDll 从路�?path 或内存数�?strMemoryDll 中加�?DLL 模块，然后我们可以使�?dll.api 函数声明我们需要用到的api函数�?
如果自内存加�?DLL，可选使�?shareName 参数指定多线程共享名�?指定 shareName 后，多个线程可共享同一内存DLL模块，指�?shareName 参数后可省略参数@1 —�?此时仅查找已加载的DLL�?
callingConvention 参数指定默认调用约定，可省略，不指定时默认值为 "stdcall" 。操作系�?API 使用默认�?"stdcall" 调用约定。C 语言编写�?DLL 一般会使用 C 语言调用约定 "cdecl" 。callingConvention 最常见的参数就�?"stdcall" 或�?"cdecl"。更多细节请查看 [DLL 调用约定](#calling-convention)�?
加载内存 DLL 示例�?
```aardio aardio
dllmodule := raw.loadDll($"d:\\hardware.dll");

```

参考： [包含文件操作�?$](../../../language-reference/operator/include.html)

aardio 已默认加载以�?DLL 模块

```aardio aardio
::User32, ::Kernel32, ::Ntdll, ::Shell32

```

使用 aardio『工�?/ 转换工具 / API 转换』工具可自动转换 C/C++ �?API 函数声明为　aardio 格式，并自动识别 `::User32, ::Kernel32, ::Ntdll, ::Shell32` 这些 DLL 模块提供的函数�?
注意: [#](#arch)

> 如果 DLL 厂商仅提供一个版本的 DLL，一般是 32 位的 DLL，在 aardio 可以直接加载�?aardio 程序也是 32 位的，�?32 位程序兼容所有平台，�?64 位程序只能运行在 64 位平台�?如果 DLL 厂商提供�?64 位�?2 位两个版本的 DLL，这时候你需要选择 32 位版本的 DLL 才能加载，如�?对方只提�?64 位的 DLL (比较罕见)，只要包装为进程调用，aardio 仍然可以支持�?aardio 做多进程、多线程开发都非常方便�?通过多进程交互，aardio 就可以非常方便地调用 64 位的组件�?>
> 一个常见的误解是认�?32 位不能调�?64 位程序，其实这种限制仅仅是进程内的限制，对跨进程调用并没有限制。而且目前跨进程调用更为普及，稳定性与兼容性都更好。典型的最常见的浏览器应用就是多进程架构。在 aardio 中利用标准库中的　web.view 就可以非常方便地调用 64 位的 WebView2 组件�?>
> aardio 中多进程组件以及可以用于多进程架构的库非常多，包括但不限�?web.view, process, process.popen, process.ruffle, process.python, process.command，process.rpc, web.rpc, web.socket, process.util,com,com.excel,com.activeX …�?
## 二、声�?API 函数 [\#](\#api)

1. 语法�?

   ```aardio aardio
   var dll = raw.loadDll( path | strMemoryDll,shareName,callingConvention="stdcall" );

   dll.api( 函数名|函数序号,函数原型,调用约定="stdcall",this指针=null)

   ```

2. 说明

   这里�?dll �?raw.loadDll 加载�?dll 模块对象�?
   dll.api 函数的第一个参数是加载�?DLL 模块中导出的 API 函数名字，或导出函数序号�?
   调用约定为可选参数，默认为加�?DLL 模块时指定的调用约定。如果加�?DLL 时未指定调用约定，则默认值为 "stdcall"。更多细节请查看 [API 调用约定](#calling-convention)�?
   可选的 this 指针参数用于 thiscall 调用约定绑定 C++ �?this 对象的指针，也可用于其他调用约定中指定默认的第一个参数�?
   函数原型是以一个字符串表示�?API 函数声明，定义该函数的参数类型、返回值类型等, 这里的类型指原生数据类型. 例如:

   `"int(int a,int b)"`

   定义了一个函数原�?有一�?int 类型的参数a,一�?int 类型的参�?b,返回值为 int 类型�?
   请参�? [原生数据类型](datatype.html)

3. UTF-16 API 与尾�?[#](#api-name-suffix)

   aardio 支持�?Unicode 版本 API 的字符串参数进行 UTF-16 �?UTF-8 编码的双向自动转换�?
   请参考： [Unicode（UTF-16�?API 函数](utf16.html)

   API 尾标指的�?API 函数名尾部独立大写的特定字符。使用尾标可以修改默认的 API 调用规则�?

   - 尾标必须是函数名的最后一个大写字母，前面不能有其他大写字母�?   - 无论真实�?API 函数名是不是包含实际的尾标字母，我们都可以在函数名后使用尾标并且尾标起的作用是相同的�?   - aardio 会首先查找函数名称包含指定尾标的 API 函数。如果没有找到指定的 API 函数，aardio 会移除函数名称后面的尾标字母再次查找 API 函数�?   - aardio 在找不到目标函数时，总是会自动加�?'W' 尾标寻找是否存在 Unicode 版本的函数�?
在声�?API 时，可支�?'W'�?A' 两种尾标�?
[免声�?API 再可以支持更多尾标。](directCall.html#api-name-suffix)

如果 API 函数名以 '\_w' 结尾也会切换�?Unicode 版本，但 '\_w' 不是尾标字母�?\_w' 不能省略，aardio 也不会自动移�?'\_w' �?自动添加 '\_w' 然后查找 API 函数�?
如果不写函数原型参数，使�?`dll.api("导出符号�?)` 格式搜索 DLL 导出符号�?aardio 不会自动添加或移除尾标�?
4. 声明原生 API 示例


   ```aardio aardio
   //导入DLL
   var dll = raw.loadDll("User32.dll");

   //声明 API
   messageBox = dll.api( "MessageBox", "void(int hWnd,ustring lpText,ustring lpCaption ,INT uType )","stdcall") //最后一个参数可以省�?
   //调用 API 函数
   messageBox( 0, "这是一个测试对话框", "对话框标�?, 0 )

   ```


   要注�?MessageBox 并不存在，aardio 会自动切换到 MessageBoxW ，并识别 ['W' 尾标](#api-name-suffix)，切换到 [Unicode( UTF-16 ) API](utf16.html) ，然后参字符串参数与返回值进�?UTF-8 �?UTF-16 编码双向自动转换�?
   aardio 已经默认导入�?`::User32, ::Kernel32, ::Ntdll, ::Shell32` 这几�?DLL 模块，所以上面的代码可简化为�?

   ```aardio aardio
   messageBox = ::User32.api( "MessageBox", "void(int hWnd,ustring lpText,ustring lpCaption ,INT uType )","stdcall") //最后一个参数可以省�?
   //调用 API 函数
   messageBox( 0, "这是一个测试对话框", "对话框标�?, 0 )

   ```


   aardio 其实 [不用声明也可以直接使�?DLL 导出�?API 函数](directCall.html)，一般除非是有什么不能自动转换的类型，不必要先声明，aardio 提倡无声明直接调用 API 函数，例如：


   ```aardio aardio
   ::User32.MessageBox(0,"这是一个测试对话框","对话框标�?,0)

   ```


### 三、声明内部函�?[\#](\#function-pointer)

语法�?
```aardio aardio
var dll = raw.loadDll();
var func = dll.api( 内部指针地址,函数原型 )

```

如果调用 raw.loadDll() 时未使用任何参数，则 dll.api 的第一个参数应当是一个内部函数指针�?
实际�?aardio 已经用以下的代码默认加载�?raw.main 模块�?
```aardio aardio
raw.main = raw.loadDll();

```

所以我们可以直接写�?
```aardio aardio
var func = raw.main.api( 内部指针地址,函数原型 )

```

一个有趣的示例(危险操作,请勿模仿):

```aardio aardio
import win;

var func = function(str){ win.msgbox( "非法操作:" + str) }

//转换为原生函数指�?var func_c = raw.tostdcall(func,"void(str)" )

//获取原生指针，对内核对象使用 topointer,tonumber 等函数是无效�?funcAddr = raw.toPointer(func_c)

//声明一个特殊的API,调用内部函数指针
func_api = raw.main.api( funcAddr ,"void(str)" )

//看来是一件很无聊的事,转来转去,我们只是调用 aardio 函数而已.
func_api("hello")

```

## 四、API 调用约定 [\#](\#calling-convention)

加载 DLL 与声�?API 时都可选指定调用约定参数�?
调用约定参数也可以不指定，默认值为"stdcall"，可选值为"cdecl","thiscall"�?fastcall"�?regparm(n)"�?

可以在调用约定后面紧跟一个逗号以及目标 DLL 的开发平台，可选值为",borland"�?",microsoft" 。microsoft 是默认选项可以省略。实际上需要用�?",borland" 这个选项的情况现在基本遇不到了，即使是调�?Delphi 编写�?DLL�?stdcall","cdecl" 等调用约定都不需要指定开发平台�?
"thiscall" �?C++ 对象调用约定，可在声�?API 时增加一个参数指�?this指针，如果不在声明时指定，也可以在调用时用首参数传�?this 指针�?
fastcall,regparm(n) 调用约定( 也就是寄存器传参方式 ) 详解:

> "fastcall"
> "fastcall,microsoft"
> 以上两种写法作用相同，前2个小于等�?2位的数值参数使用edx,ecx寄存器， > 如果还有参数则自右向左依次压�? 由被调者负责维护堆栈平�?清除压入的参> �?;如果函数有返回值则把返回值存放在eax寄存器中.
>
> "fastcall,borland"
> 同上，前3个小于等�?2位的数值参数使用eax,edx,ecx寄存器，
>
> "fastcall,regparm(n)"
> "stdcall,regparm(n)"
> 以上两种写法作用相同，n可以�?,2,1,前n个参数使用eax,edx,ecx寄存�?如果�?则仅使用eax，为2仅使用eax,edx
>
> "regparm(n)"
> "cdecl,regparm(n)"
> 以上两种写法作用相同，n可以�?,2,1,前n个参数使用eax,edx,ecx寄存�?如果�?则仅使用eax，为2仅使�?eax,edx 。如果还有参数则自右向左依次压栈; 由调者负责维护堆栈平�?清除压入的参�?;如果函数有返回值则把返回值存放在eax寄存器中.

在调�?raw.loadDll 函数时，可以在调用约定中添加 ",unicode" 声明�?DLL 的所�?API �?[UTF-16 API](utf16.html) 。例如： `raw.loadDll("test.dll",,"stdcall,unicode")` 声明�?"test.dll" 中所�?API �?UTF-16 API 。但要注意每�?API 函数仍然可以声明自己是不同的编码，API 参数也可以使用参数类型明确的声明是文本还是二进制字符串�?
### 五、DLL 导出符号 [\#](\#dllimport)

1. 语法�?

   ```aardio aardio
   var dll = raw.loadDll();
   var ptr = dll.api( "导出符号�? )

   ```

2. 说明�?
   dll.api 仅指定一个参数时直接返回导出符号指针而非返回原生函数对象�?
   查找导出符号时会精确匹配"导出符号�?，不会对"导出符号�?自动添加或移�?A,W 尾标�?
   此操作不会增�?DLL 的引用计数，在使用导出符号指针时 DLL 模块对象应在生存周期内�?
   使用此方法可以获�?DLL 导出的数据指针，或者用精确匹配函数名的方式获取 DLL 的导出函数指针�?
3. 示例


   ```aardio aardio
   //取到 DLL 导出函数指针
   var pMsgbox = ::User32.api("MessageBoxW");

   //将函数指针转换为函数
   var msgbox = raw.main.api(pMsgbox,"void(int,ustring,ustring,int)" );

   //调用函数
   msgbox(0,"消息","标题",0);


   ```


   实际调用 DLL 导出函数不需要这么复杂，直接调用就可以了，例如：


   ```aardio aardio
   //调用 DLL 导出函数
   ::User32.MessageBox(0,"消息","标题",0);

   ```


[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-guide/builtin/raw/api.md)

