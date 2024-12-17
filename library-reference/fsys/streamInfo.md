[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.streamInfo 库模块帮助文�?
## fsys 成员列表

### fsys.streamInfo

用于获取文件或目录的全部数据流名�?

NTFS 文件系统支持 Alternate Data Streams 特�?

允许同一文件或目录附加存储多个命名数据流,

普通读写文件默认访问的是主数据流（未命名流�?

备用数据流（命名流）默认是不可见的，

通过在文件名�?\+ ":" \+ "流名�? 可读写命名数据流

用于获取文件或目录的全部数据流名�?

成功返回数组,失败返回 null,错误代码,

如果传入不存在或非NTFS分区的文件路径则返回 null

因为#操作符可用于null或数�?

可用#操作符判断是否存在命名数据流

### fsys.streamInfo(path)

用于获取文件或目录的全部数据流名�?

@path 参数指定文件或目录路�?

成功返回数组,失败返回 null,错误代码

### fsys.streamInfo(path,mode,shareMode,creation,flagsAndAttributes,secAttrib)

用于获取文件或目录的全部数据流名�?

@path 参数指定文件或目录路�?

其他所有参数与 fsys.file 相同,

一般不必指定这些参�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/streamInfo.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/streamInfo.md')

