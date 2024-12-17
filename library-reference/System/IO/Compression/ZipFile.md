[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# System.IO.Compression.ZipFile 库模块帮助文�?
## System.IO.Compression.ZipFile 成员列表

.Net System.IO.Compression.ZipFile 名字空间

支持 .NET 4.5 及以上，Win10 以及更新的系统已自带

### System.IO.Compression.ZipFile.?

.NET 名字空间、类、结构体的成员，

可访问成员名字空间、类、枚举、静态属性或字段�?
导入的类可用于构�?.NET 对象，传�?.NET 则自动转为该类的 Type 对象

[返回对象:dotNetNameSpaceObject](../../../dotNet/appDomain.html#dotNetNameSpaceObject)

### System.IO.Compression.ZipFile.CreateFromDirectory

简单压缩目录到 zip 文件�?
如果需要更多功能请改用 zlib.zip �?
### System.IO.Compression.ZipFile.CreateFromDirectory(源目录路�?zip文件路径,压缩级别,是否包含根目录名)

简单压缩目录到 zip 文件

如果 zip 文件存在会报错，请先�?io.exist 判断一�?

路径请用 io.fullpath 转换为绝对路径�?
压缩级别�?0 表示优化，为 1 表示速度优化，为 2 不压�?
### System.IO.Compression.ZipFile.ExtractToDirectory

简单解压缩 zip 文件�?
如果需要更多功能请改用 zlib.unzip �?
### System.IO.Compression.ZipFile.ExtractToDirectory(zip文件路径,目标目录路径)

简单解压缩 zip 文件

路径请用 io.fullpath 转换为绝对路�?
### System.IO.Compression.ZipFile.assembly

导入�?.NET 名字空间的程序集对象�?
[返回对象:dotNetCrlAssemblyObject](#dotNetCrlAssemblyObject)

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/System/IO/Compression/ZipFile.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/System/IO/Compression/ZipFile.md')

