[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.batch 库模块帮助文�?
## fsys 成员列表

### fsys.batch

批量替换文件数据

创建批处理对象�?
### fsys.batch()

[返回对象:fsysBatchObject](#fsysBatchObject)

### fsys.batch(批处理目�?文件�?文件编码)

创建批处理对象�?
参数 @1 指定目标目录�?
参数 @2 指定文件名，支持通配符，例如 "\*.\*"，也可以指定文件名数组�?
参数 #2 可选指�?enumText 函数读取文件的默认编码�?
## fsysBatchObject 成员列表

### fsysBatchObject.dir

设置批处理目�?
### fsysBatchObject.enumBinary(回调函数,路径模式匹配�?

```aardio aardio
fsysBatchObject.enumBinary(
    function(content,fullpath){
        return /*返回 string 类型数据新文�?返回false 终止,返回空忽�?/;
    }
    /*,可选指定路径模式匹配串,可选指定文件编�?/
)

```

### fsysBatchObject.enumText(回调函数,路径模式匹配�?文件编码)

```aardio aardio
fsysBatchObject.enumText(
    function(utf8Text,codepage,fullpath){
        var utf8Text,count = string.replace(utf8Text,"@查找字符�?,"替换字符�?);
        if(count){
            return utf8Text,codepage;/*返回文本�?codepage 以指定内码更新文件�?返回�?2 也可返回指定 Unicode 编码的字符串，例�?"UTF-8-NOBOM"�?仅返回文本以 UTF-8 编码更新文件,
返回 false 终止,返回空忽�?/
        }
    }
)

```

### fsysBatchObject.enumTo(回调函数,目标目录,路径模式匹配�?

```aardio aardio
fsysBatchObject.enumTo(
    function(dstPath,srcPath){
        fsys.copy(srcPath,dstPath);
        return /*srcPath 为源文件路径,
dstPath 为目标文件路�?
此函数根据源目录生成目标目录下相同结构的路径,
自动在目标目录下建立相同的子目录结构,
得不会复制或删除文件文件
返回 false 终止*/
    },"/目标目录"
)

```

### fsysBatchObject.wildcard

设置批处理文件名掩码

默认�?\*.\*"

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/batch.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/batch.md')

