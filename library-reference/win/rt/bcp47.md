[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.rt.bcp47 库模块帮助文�?
## win.rt.bcp47 成员列表

BCP47语言标签相关函数�?

支持 Win8 以及 Win8 以后的操作系�?

Windows Vista 及以后版本，采用 RFC 4646 作为语言标签�?
字符串最大长�?85，包含了结尾的零字符

请参考相关库 sys.locale ,string.conv

### win.rt.bcp47.getAbbreviation(bcp47lang)

返回指定语言的缩写名�?

例如中文返回"简�?,英文返回"ENU",

参数指定 BCP47 语言缩写标签

### win.rt.bcp47.getInputMethods()

返回所有启用的输入�?
### win.rt.bcp47.getIsoCode(bcp47lang)

参数指定 BCP47 语言缩写标签,

返回对应�?ISO 语言代码

### win.rt.bcp47.getName(bcp47lang)

返回指定语言的完整名�?

参数指定 BCP47 语言缩写标签

### win.rt.bcp47.getUserLanguageInputMethods(bcp47lang)

返回指定语言所有启用的输入�?

参数指定 BCP47 语言缩写标签

### win.rt.bcp47.getUserLanguages()

返回所有启用的 BCP47 语言缩写标签

### win.rt.bcp47.lcidFrom(bcp47lang)

参数指定 BCP47 语言缩写标签,

返回对应�?LCID 数�?
### win.rt.bcp47.setUserLanguages()

设置系统语言,进程需要管理权�?

参数可以指定 BCP47 语言缩写标签组成的数�?

也可以传入一个字符串，并且分号分隔所有BCP47 语言缩写标签

### 全局常量

### ::Bcp47Langs

标准�?win.rt.bcp47 加载的系统DLL组件,

�?Win8 以及 Win8 以后的系统支持此组件,

[返回对象:dllModuleObject](../../raw/_.html#dllModuleObject)

### ::Winlangdb

标准�?win.rt.bcp47 加载的系统DLL组件,

�?Win8 以及 Win8 以后的系统支持此组件,

[返回对象:dllModuleObject](../../raw/_.html#dllModuleObject)

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/rt/bcp47.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/rt/bcp47.md')

