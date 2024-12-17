[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.clip.data 库模块帮助文�?
## win.clip 成员列表

### win.clip.data

剪贴板读写自定义格式数据

### win.clip.data()

创建剪贴板自定义格式�?
参数 @1 用一个字符串指定格式名称�?
例如 RTF 格式�?"Rich Text Format"

[返回对象:winClipDataObject](#winClipDataObject)

## winClipDataObject 成员列表

### winClipDataObject.read()

读取自定义格式数据�?
成功返回 buffer 对象�?
### winClipDataObject.readText()

读取 Unicode（UTF-16）编码文本并返回 UTF-8 编码文本�?
### winClipDataObject.write(剪贴板数�?

写入自定义格式数据，不清空剪贴板原来的数据�?
参数@1�?buffer �?string 对象�?
成功返回剪贴板数据句�?
### winClipDataObject.write(剪贴板数�?true)

写入自定义格式数据，清空剪贴板原来的数据�?
参数@1�?buffer �?string 对象�?
成功返回剪贴板数据句�?
### winClipDataObject.writeText(剪贴板数�?

�?UTF-8 编码文本转换�?Unicode（UTF-16）编码写入剪贴板�?
不清空剪贴板原来的数据�?
成功返回剪贴板数据句�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/clip/data.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/clip/data.md')

