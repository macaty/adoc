[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sys.reg 库模块帮助文�?
## sys.reg 成员列表

简单写注册�?
如果需要更多功�?请改�?win.reg

### sys.reg.setValue

写注册表

### sys.reg.setValue(name,value,path,root)

写注册表�?
@name 使用字符串指定值名称（null �?空串表示默认值）�?
@value 可指定数值、字符串、buffer、null

数值为存为 \_REG\_DWORD 类型,

字符串值存�?\_REG\_SZ 类型,

buffer 值存�?\_REG\_BINARY 类型�?

null 值表示删除�?
参数 @path 使用字符串指定注册表路径,

参数 @root 指定注册表根�?省略则默认为 \_HKEY\_CURRENT\_USER

### 全局常量

### ::Advapi32

Advapi32.dll 模块

以下标准库已加载该模�?

crypt,process,service,sys,sys.reg,win.reg

[返回对象:dllModuleObject](../raw/_.html#dllModuleObject)

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/sys/reg.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/sys/reg.md')

