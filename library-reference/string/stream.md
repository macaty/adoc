[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# string.stream 库模块帮助文�?
## string 成员列表

### string.stream()

[返回对象:StringStreamObject](#StringStreamObject)

### string.stream(文件路径)

支持资源文件,

参数也可以是普通字符串内容,

创建的流是只读的

## StringStreamObject 成员列表

### StringStreamObject.read(长度)

读取内容,返回字符�?
### StringStreamObject.readBuffer

读取数据�?buffer ,成功返回读取长度,失败返回null

### StringStreamObject.readBuffer(buffer,读取长度)

直接读数据到内存

参数@1可以�?buffer 对象,或内存指�?

如果是指针则必须指定读取长度,否则长度参数可�?
成功返回读取长度

### StringStreamObject.seek(偏移数�?"set")

移动流指�?

参数@2为以下�?

"set":相对文件开�?

"end":相对文件�?

"cur":相对当前位置

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/string/stream.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/string/stream.md')

