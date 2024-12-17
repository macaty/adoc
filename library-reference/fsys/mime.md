[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.mime 库模块帮助文�?
## fsys.mime 成员列表

### fsys.mime.fromData(字符串数�?网址,默认MIME,选项)

获取MIME类型

除参数@1以外，其他参数可以省�?

默认MIME建议设为 "text/html"

此函数失败也会返�?application/octet-stream"

### fsys.mime.fromFile(文件路径,选项)

获取MIME类型,参数@2可以省略,

注意文件路径可以指向不存在的文件,根据文件后缀名检测MIME

此函数失败也会返�?application/octet-stream"

### fsys.mime.fromUrl(网址,选项)

获取MIME类型,参数@2可以省略,

此函数失败也会返�?application/octet-stream"

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/mime.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/mime.md')

