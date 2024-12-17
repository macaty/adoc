[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# inet.urlData 库模块帮助文�?
## inet 成员列表

### inet.urlData(data,path,mime)

参数 @1 可指定字符串�?buffer，如果为 null 则自参数 @2 指定的路径加载数据�?
参数 @2 指定文件路径，如果用于获�?MIME 可指定并非实际存在的文件名�?
可选指�?MIME，如不指定则自参�?@2 指定的路径获�?MIME�?
## inet.urlData 成员列表

生成 Data URL

返回 Data URL

### inet.urlData.parse

解析 Data URL 并返回解析后数据

### inet.urlData.parse(url)

如果参数不是字符串返�?null �?
如果参数�?Data URL，返回解析后的数据与 MIME。\\如果数据�?base64 编码则自动解码�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/inet/urlData.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/inet/urlData.md')

