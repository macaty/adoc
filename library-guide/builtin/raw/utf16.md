[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# Unicode（UTF-16�?API 函数

原生 API、Windows API 里的 Unicode API 一般使用的�?UTF-16 编码�?
�?aardio 字符串默认使用的�?UTF-8 编码�?也可以存储非 UTF-8 编码的任何二进制字符�?）。aardio 也可以创�?UTF-16 字符串（ ustring ），并支持转换或自动转换 UTF-8 �?UTF-16 编码字符串�?
如果原生 API 使用的是 UTF-8 编码，那么与 aardio 字符串完全一致，没有任何需要处理的编码问题�?
## 自动转换 Unicode(UTF-16) 字符�?[\#](\#conv)

当我们编写以�?aardio 代码调用原生 API 函数�?
```aardio aardio
::User32.MessageBox(0,"消息","标题",0)

```

aardio 将会检测出 ::User32.MessageBox 需�?UTF-16 编码的字符串参数，然后自动将字符串参数转换为 UTF-16 编码。这一切都是自动完成的，非常方便�?
Unicode API 如果有输出字符串�?
aardio 也会自动将其转换�?aardio 默认�?UTF-8 编码�?
aardioUnicode(UTF-16) APIUTF-8 编码<双向自动转换>UTF-16 编码

## Unicode（UTF-16�?API 函数 [\#](\#utf16-api)

在调�?raw.loadDll 加载 DLL 时，如果在调用约定参数中添加 `,unicode` 则可以声明该 DLL 的所�?API 默认�?Unicode（UTF-16�?API ，字符串使用 UTF-16 编码�?
示例�?
```aardio aardio
var dll = raw.loadDll("utf16.dll",,"stdcall,unicode")

```

即使 DLL 对象声明了默认使�?Unicode ( UTF-16 ) 编码�?这个 DLL 加载�?API 函数仍然可以使用不同的编码规则�?
API 函数可以通过函数名字的尾标声明或自动识别 UTF-16 API�?
- 尾标必须是函数名的最后一个大写字母，前面不能有其他大写字母�?- 无论真实�?API 函数名是不是包含实际的尾标字母，我们都可以在函数名后使用尾标并且尾标起的作用是相同的�?- aardio 会首先查找函数名称包含指定尾标的 API 函数。如果没有找到指定的 API 函数，aardio 会移除函数名称后面的尾标字母再次查找 API 函数�?- aardio 在找不到目标函数时，总是会自动加�?'W' 尾标寻找是否存在 Unicode 版本的函数�?
声明 API 或免声明直接调用 API 都可以支�?'W'�?A' 尾标�?
- 'W' 尾标：用以确定或声明一�?API �?UTF-16 API 函数，用于指�?aardio 需要对字符串做 UTF-16 �?UTF-8 编码的双向自动转换�?
- 'A' 尾标�?�?aardio 中并不是�?"ANSI" 而是�?"Any" ，用于指�?aardio 字符串可以包含任何内容，不要做自动编码转换。当然字符串可以包含 UTF-8 或�?ANSI 编码或任何其他数据�?

免声明调�?API 时，Unicode API 里所有字符串类型的参数会自动转换编码，buffer 不会自动转换编码�?
## Windows API 版本切换 [\#](\#win)

Windows API�?WinAPI �?函数名以 'W' 尾标表示 Unicode ( UTF-16 ) API，而以 'A' 尾标表示相同函数�?ASNI 版本�?
虽然 Windows API �?'W'�?A' 尾标规则�?aardio 兼容，但仍要强调 'A' 尾标�?aardio 里表�?"Any" 而不�?"ANSI"�?
对于同时提供 ANSI，UNICOD 两个版本�?WinAPI 函数，函数名不指�?'W'�?A' 后缀明确指定版本时， aardio 将会自动选择 Unicode 版本 API。大多数 WinAPI 支持这种自动切换，例�?::User32.MessageBox�?
但是有少�?WinAPI 不但提供�?'W'�?A' 后缀的版本，还会提供不带 'W'�?A' 后缀的版本，这时候需要明确指�?'W'�?A' 后缀，或者明确指定正确的字符串参数类型�?
## API 声明中的参数类型�?Unicode（UTF-16）编码转�?[\#](\#args)

声明或确定一�?Unicode API 主要影响的是免声明调用�?
对于声明后调�?API�?'W'�?A' 尾标的主要作用是帮助我们选择不同版本�?API 函数�?
在声�?API 函数并指定参数类型的情况下，只有声明�?str 类型的参数在 Unicode API 里会执行�?ustring 相同的行为并自动转换编码。在�?Unicode API �?str 类型只是处理为普通文本参�? �?`'\0'` 为终止符�?C 字符�?）�?
无论是不�?Unicode API�?
API 函数声明里的其他类型则始终遵守相同的规则�?
- 声明�?ustring / USTRING 的参数总是会自动转换编码�?- 声明�?string 类型总是�?aardio 认为是二进制数据，不会自动转换编码�?- 声明�?buffer、指针（pointer）等类型总是被认为是二进制数据，不会自动转换编码�?
### 原生类型 ustring / USTRING [\#](\#ustring)

声明为原�?ustring / USTRING 类型�?API 参数，我们可以传 UTF-16 字符串，也可以传 aardio 默认�?UTF-8 编码字符串�?
aardio �?ustring / USTRING 类型会做双向的自动编码转�?
aardio原生 APIstring�?UTF-8 编码�?双向自动转换>ustring( UTF-16 编码 )

原生类型 ustring 支持以下 aardio 值：

- 字符串，默认 UTF-8 编码
- UTF-16 字符串（ ustring ），自动转换编码
- buffer，不会自动转换编�?- 指针，不会自动转换编�?- null

大写的原生类�?USTRING 不允许传 null 值，其他与小写的 ustring 类型相同�?
### API结构体类�?`word[] WORD []` [\#](\#word-array)

`word[] WORD []` 等原生组类型，如果对应字段没有赋值为一个表数组，则会做双向的自动编码转换�?
aardio原生 APIstring�?UTF-8 编码�?双向自动转换>ustring( UTF-16 编码 )

例如�?
```aardio aardio
{ WORD s[] = "abc"; }

```

上面的结构体占用 6 个字节�?上面的结构体，原�?API 看到的总是 `'abc'u` 这样�?UTF-16 字符串（ustring），一个字符占 2 个字节。但是在 aardio 里看到的就是 "abc" 这样�?UTF-8 字符串，英文字母�?1 个字节�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-guide/builtin/raw/utf16.md)

