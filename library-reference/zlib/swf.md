[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# zlib.swf 库模块帮助文�?
## zlib 成员列表

### zlib.swf

swf文件压缩解压�?
### zlib.swf("swf文件路径")

创建swf文件对象

### zlib.swf()

[返回对象:zlibswffileObject](#zlibswffileObject)

## zlibswffileObject 成员列表

### zlibswffileObject.compress()

压缩

成功返回true,

可选参参数中指定存储路�?不指定则修改原文�?

如果已经是压缩格式不操作直接返回false

### zlibswffileObject.header.data

原始文件数据

### zlibswffileObject.header.sig

压缩格式�?FWS"

非压缩格式为"CWS"

### zlibswffileObject.header.size

原始文件大小

### zlibswffileObject.header.version

版本

### zlibswffileObject.path

swf文件路径

压缩或解压后会修改该路径为最后存储的位置

### zlibswffileObject.uncompress()

解压�?
成功返回true,

可选参参数中指定存储路�?不指定则修改原文�?

如果文件已经是非压缩格式不操作直接返回false

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/zlib/swf.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/zlib/swf.md')

