[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# web.multipartFormData 库模块帮助文�?
## web 成员列表

### web.multipartFormData

用于构建上传文件表单

### web.multipartFormData()

构建上传文件表单

[返回对象:webMultipartFormDataObject](#webMultipartFormDataObject)

## webMultipartFormDataObject 成员列表

### webMultipartFormDataObject.add("字段�?,"@�?)

添加字段到上传表单中

如果值的第一个字符为"@",则@后面应当是上传文件路�?
### webMultipartFormDataObject.addFile("字段�?,"文件路径")

添加文件到上传表单中

### webMultipartFormDataObject.addTable(字段名值对)

```aardio aardio
webMultipartFormDataObject.addTable(
    [""] = "@/*如果值的第一个字符为"@",则@后面应当是上传文件路�?/";
    [""] = "";
);

```

### webMultipartFormDataObject.close()

关闭对象

无需手动调用该函�?
### webMultipartFormDataObject.codePage

指定服务端编码使用的代码�?
数�?UTF8编码�?5001,系统默认ANSI编码�?,null为默认UTF8编码

### webMultipartFormDataObject.contentHeader()

返回一个用于构建HTTP头的�?指定了Content-Type的�?

"multipart/form-data; boundary=分隔�?

可选在参数中指定多个附加表用于添加更多键�?
### webMultipartFormDataObject.contentType()

返回请求HTTP头Content-Type的�?

"multipart/form-data; boundary=分隔�?

### webMultipartFormDataObject.read(块大�?

读取上传数据

应循环调用该函数,直到该函数返回空�?
### webMultipartFormDataObject.readAll(块大�?

读取所有数�?
### webMultipartFormDataObject.size()

获取上传数据总大�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/multipartFormData.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/multipartFormData.md')

