[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.info 库模块帮助文�?
## fsys.info 成员列表

### fsys.info.get

返回文件信息

### fsys.info.get("路径",SHGFI\_... )

参数@2指定一个或多个选项,多个选项用\|连接,

如果参数@2指定了\_SHGFI\_USEFILEATTRIBUTES,

则参数@3必须�?_FILE\_ATTRIBUTE_ 前缀常量指定文件属�?
### fsys.info.get()

[返回对象:shFileInfoObject](#shFileInfoObject)

### fsys.info.getExeType()

[返回对象:fsysExeInfoExeTypeObject](#fsysExeInfoExeTypeObject)

### fsys.info.getExeType(文件路径)

检测是否EXE文件

失败返回�?
## fsysExeInfoExeTypeObject 成员列表

### fsysExeInfoExeTypeObject.magic

DOS程序�?MZ"

非DOS程序�?PE"

### fsysExeInfoExeTypeObject.winVer

控制台程序为0

GUI 程序�?Windows 版本�?

Windows 版本号参考： [https://docs.microsoft.com/en-us/windows/win32/winprog/using-the-windows-headers](javascript:if(confirm('https://docs.microsoft.com/en-us/windows/win32/winprog/using-the-windows-headers  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ����һ������·���ⲿ������Ϊ������ʼ��ַ�ĵ�ַ��  \n\n�����ڷ������ϴ�����?'))window.location='https://docs.microsoft.com/en-us/windows/win32/winprog/using-the-windows-headers')

## shFileInfoObject 成员列表

### shFileInfoObject.dwAttributes

文件属�?
### shFileInfoObject.hIcon

图标句柄

如果不为空要负责释放该句�?
### shFileInfoObject.iIcon

在图像列表中的索�?
### shFileInfoObject.returnValue

SHGetFileInfo的返回�?
### shFileInfoObject.szDisplayName

文件�?
### shFileInfoObject.szTypeName

类型�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/info.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/info.md')

