[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# win.path 库模块帮助文�?
## win.path 成员列表

### win.path.add

添加文件路径到当前进程的指定环境变量

### win.path.add(path,name,last)

添加 @path 指定的文件路径到当前进程的指定环境变�?

可选用 @name 参数指定环境变量�?默认值为"Path",

可选参�?@last 如果�?true,

则添加到其他已存在的路径后面,否则插入到最前面

### win.path.get()

返回PATH环境变量中的目录路径数组

### win.path.search("字符串参�?)

以当前目录、应用程序目录、EXE目录、系统目�?path环境变量指定的目录下查的文件

### win.path.searchDll()

按系统加载DLL的查找规则查找DLL文件,

如果指定多个参数,只要一个参数指定的DLL没找到即返回null

如果所有指定的DLL都找到了,返回最后一个参数指定的DLL完整路径

### win.path.update(user,name)

自注册表读取指定环境变量的最新�?

并更新当前进程的环境变量,

以避免使用旧的值或从父进程继承了旧的�?

参数@user 如果指定�?true,则读取用户环境变量�?
默认读取系统环境变量,

可选用 @name 参数指定环境变量�?默认值为"Path"

使用此函数之前调用代码必须自行导�?win.reg �?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/path.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/path.md')

