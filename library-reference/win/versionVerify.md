[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# win.versionVerify 库模块帮助文�?
条件表达式语�?
支持�?&& 逻辑运算法连接多个条件表达式�?支持�?==, <, <=, >, >= 等关系运算符判断版本号，
支持�?&, \| 等按位运算符判断 suiteMask�?不支持其他操作符�?
一般建议用 >= �?<= , 而非 > �?<,
�?\> �?< 可能实际检测用的是>= �?<=�?
## win 成员列表

### win.versionVerify("major >= 10 && minor >=0 ")

用于验证操作系统版本

参数中指定条件表达式,可支持的操作符和变量请查看源代码

建议使用标准�?win.version 获取系统版本,

或使�?aardio 提供的全局常量:

\_WINXP \_WIN7\_LATER \_WIN10\_LATER \_WINE

快速判断操作系统版�?
## win.versionVerify 成员列表

### win.versionVerify.isServer()

操作系统版本是否服务器版�?
### win.versionVerify.isWin10Later()

是否 Windows 10 以及 Windows 10 以后的系�?

建议直接用全局常量 \_WIN10\_LATER 判断更快更快方便

### win.versionVerify.isWin11Later()

是否 Windows 11 以及 Windows 11 以后的系�?
### win.versionVerify.isWin7Later()

是否 Windows 7 以及 Windows 7 以后的系�?

建议直接用全局常量 \_WIN7\_LATER 判断更快更快方便

### win.versionVerify.isWinXp()

是否 Windows XP 系统

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/versionVerify.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/versionVerify.md')

