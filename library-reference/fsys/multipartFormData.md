[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.multipartFormData 库模块帮助文�?
## fsys 成员列表

### fsys.multipartFormData

multipart/form-data格式文件解析�?
### fsys.multipartFormData("文件路径","分隔�?)

解析文件返回表对�?
可选在参数@3中指定读写缓冲区大小

### fsys.multipartFormData()

```aardio aardio
!stdfsysmultipartFormData

```

## fsysmultipartFormDataObject 成员列表

### fsysmultipartFormDataObject.?

multipart/form-data对象的每个键名下保存每个字段的信�?
[返回对象:fsysmultipartFormFieldObject](#fsysmultipartFormFieldObject)

### fsysmultipartFormDataObject.getPath()

参数中指定的文件路径

## fsysmultipartFormFieldObject 成员列表

### fsysmultipartFormFieldObject.contentLength

数据长度

### fsysmultipartFormFieldObject.contentOffset

偏移位置

### fsysmultipartFormFieldObject.contentType

MIME类型

### fsysmultipartFormFieldObject.filename

文件�?
如果不是文件则为�?
### fsysmultipartFormFieldObject.name

字段名称

### fsysmultipartFormFieldObject.save("文件路径")

保存文件

上传文件数据如果不保�?在请求结束将被自动删�?
### fsysmultipartFormFieldObject.value()

此函数直接读取并返回此字段的数据

较大文件应使用save函数转存文件

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/multipartFormData.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/multipartFormData.md')

