[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# inet.url 库模块帮助文�?
## inet.url 成员列表

网址（URL）函数库�?
inet.http,inet.whttp 以及所�?web.rest 客户端都已经自动导入 inet.url �?
### inet.url.append

拼接URL

### inet.url.append(url目录,url子路�?...)

支持不定个数参数�?
第一个参数无论是否以"/"字符结束都认为是一个目录�?
### inet.url.appendExtraInfo(url,附加参数)

�?URL 后追加参数�?
参数首字符不能是问号�?
参数@2也可以指定一个包含多个参数键值对的表�?
如果 @url 参数仅指定路径而非合法 URL�?
则简单添�?? 号后拼接参数

### inet.url.canonicalize("当前URL",\_URL)

URL规范化转�?
参数@3指定转换选项

### inet.url.canonicalize(URL)

URL规范化转�?
扩展和适当置换路径中包含的所�?.. �?.

### inet.url.cmp()

比较参数@1与参数@2指定的网址是否相同�?
相同则返�?0 ，否则返回其他数值�?
比较前进�?URL 解码，并调用 inet.url.canonicalize 规范格式�?
比较时忽略大小写

### inet.url.decode(字符�?输入代码�?

URL解码并返回文�?失败返回空�?

参数二指定输入编�?codepage),省略自动检测输入编�?
此函数返回数据转换为UTF8编码

### inet.url.decodeUnicode(字符�?

解码%uXXXX�?uXX编码的字符串

失败返回空�?
### inet.url.encode(字符�?输出代码�?

除字母数字以�?.\_~等非保留字符以外的字符进行URL编码,

参数二指定输出编�?codepage),默认�?5001(UTF8代码�?

### inet.url.encodeMbcs(字符�?输出代码�?

如果字符串包含多字节字符,

使用URL编码其中的汉字和%符号,

参数二指定输出编�?codepage),默认�?5001(UTF8代码�?

### inet.url.encodeUri(字符�?输出代码�?

URL编码,

字母数字以及 URL 非保留字符、URL 保留字符都不编码（RFC3986�?

参数二指定输出编�?codepage),默认�?5001(UTF8代码�?

### inet.url.getFileName(网址,默认文件�?

获取URL中的文件�?
参数2可�?默认�?index.html"

### inet.url.getFilePath()

如果 URL �?file: 协议开头，

则返�?URL 解码后的文件路径，否则返�?null�?
传入 null 参数返回 null�?
### inet.url.getParams()

返回 URL 的参数表，参数名都转为小写�?
参数 @1 指定 URL，如果不指定则直接返�?null �?
如果参数 @1 指定了参数名（忽略大小写），则返回对应的字符串�?
### inet.url.hashNum(url)

返回哈希数�?
### inet.url.is(url,\_URLIS)

检测URL

### inet.url.joinpath

当对于当前URL的相对路径转换为完整 URL �?
注意该函数忽略文件名,简单拼接请使用 append 函数替代

### inet.url.joinpath("当前URL",相对路径,\_URL)

当对于当�?URL 的相对路径转换为完整 URL �?
相对路径如果为空则直接返回参�?@1,

可选使用参数三指定转换选项

### inet.url.split()

[返回对象:inetUrlcrackObject](#inetUrlcrackObject)

### inet.url.split(输入URL)

拆分URL返回包含协议、路径、端口、参数等的表对象

返回的表对象可以调用 tostring 重新生成 URL

可传入空值以获取用于拼接URL的表

### inet.url.splitParameters

拆分URL参数并返回名值对组成的表对象

名字都转换为小写,如果名字尾部有\[\]或\[键名\]则值转换为�?
如果只指定名字不指定�?则值为空字符串

### inet.url.splitParameters(URL参数,分隔�?输入UTF8编码,数组键名)

拆分URL参数并返回表对象�?
分隔符支持模式语�?默认�?&'�?
如果不指定分隔符,并且首字符是?号，此函数自动移除首字符�?
使用 URL 解码键值文�?参数 @3 指定解码前是否UTF8编码，不指定则自动检测�?
参数 @4 可选指定一个总是返回数组值的参数名称数组，参数名尾部如果有点号加数值则自动移除�?
### inet.url.stringify(urlInfo)

```aardio aardio
inet.url.stringify(
    scheme = "https";
    user = "";
    password ="";
    host ="/*使用参数表构建并返回URL字符�?/";
    location = "";
    extraInfo = {
        name = value;
    };
)

```

### inet.url.stringifyParameters

将URL参数表转换为字符�?
### inet.url.stringifyParameters(参数�?输出代码�?排序函数)

使用'='分隔键值对,使用'&'分隔不同参数,

如果值为�?则转换为多个键值对,键名后添加\[\]或\[子键名\]�?
如果值为函数则调用该函数取返回值�?
所有值转换为字符串并使用 UrlEncode 编码�?
参数@2指定输出编码（codepage�?默认�?5001（UTF8代码�?

省略排序函数则使用默认字典序排序

## inetUrlcrackObject 成员列表

### inetUrlcrackObject.extraInfo

附加参数

如果有URL参数,这里首字符会�?�?
不包�?号后面的网页位置

### inetUrlcrackObject.host

域名

### inetUrlcrackObject.location

URL�?号后面的网页位置,不包�?�?
### inetUrlcrackObject.password

密码

### inetUrlcrackObject.path

文件路径;

### inetUrlcrackObject.port

端口

### inetUrlcrackObject.scheme

协议，总是转换为小�?
### inetUrlcrackObject.schemeNum

协议（数值）�?
可用值为 _INTERNET\_SCHEME_ 前缀的常量定义�?
重新拼接 URL 时忽略此参数

### inetUrlcrackObject.user

用户�?
### 自动完成常量

\_INTERNET\_SCHEME\_DEFAULT=0x0

\_INTERNET\_SCHEME\_FILE=5

\_INTERNET\_SCHEME\_FIRST=1

\_INTERNET\_SCHEME\_FTP=1

\_INTERNET\_SCHEME\_GOPHER=2

\_INTERNET\_SCHEME\_HTTP=3

\_INTERNET\_SCHEME\_HTTPS=4

\_INTERNET\_SCHEME\_JAVASCRIPT=9

\_INTERNET\_SCHEME\_LAST=0xB

\_INTERNET\_SCHEME\_MAILTO=7

\_INTERNET\_SCHEME\_NEWS=6

\_INTERNET\_SCHEME\_PARTIAL=0xFFFFFFFE

\_INTERNET\_SCHEME\_RES=0xB

\_INTERNET\_SCHEME\_SOCKS=8

\_INTERNET\_SCHEME\_UNKNOWN=0xFFFFFFFF

\_INTERNET\_SCHEME\_VBSCRIPT=0xA

\_URLIS\_URL=0x0

\_URL\_APPLY\_DEFAULT=1

\_URL\_APPLY\_FORCEAPPLY=8

\_URL\_APPLY\_GUESSFILE=4

\_URL\_APPLY\_GUESSSCHEME=2

\_URL\_BROWSER\_MODE=0x2000000

\_URL\_CONVERT\_IF\_DOSPATH=0x200000

\_URL\_DONT\_ESCAPE\_EXTRA\_INFO=0x2000000

\_URL\_DONT\_SIMPLIFY=0x8000000

\_URL\_DONT\_UNESCAPE=0x20000

\_URL\_DONT\_UNESCAPE\_EXTRA\_INFO=0x2000000

\_URL\_ESCAPE\_AS\_UTF8=0x40000

\_URL\_ESCAPE\_PERCENT=0x1000

\_URL\_ESCAPE\_SEGMENT\_ONLY=0x2000

\_URL\_ESCAPE\_SPACES\_ONLY=0x4000000

\_URL\_ESCAPE\_UNSAFE=0x20000000

\_URL\_FILE\_USE\_PATHURL=0x10000

\_URL\_INTERNAL\_PATH=0x800000

\_URL\_NO\_META=0x8000000

\_URL\_PARTFLAG\_KEEPSCHEME=1

\_URL\_PLUGGABLE\_PROTOCOL=0x40000000

\_URL\_UNESCAPE=0x10000000

\_URL\_UNESCAPE\_HIGH\_ANSI\_ONLY=0x400000

\_URL\_WININET\_COMPATIBILITY=0x80000000

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/inet/url.md)

