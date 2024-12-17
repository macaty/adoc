[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# fsys.update.maker 库模块帮助文�?
## fsys.update 成员列表

### fsys.update.maker

用于生成自动更新文件

成功返回true,失败返回空�?以及错误信息

### fsys.update.maker()

更新文件生成工具

[返回对象:fsysUpMakerObject](#fsysUpMakerObject)

## fsysUpMakerObject 成员列表

### fsysUpMakerObject.appDir

应用程序源目�?
### fsysUpMakerObject.compress(是否仅添加单个主EXE文件)

压缩并生成更新文�?
成功返回true, 失败返回null,错误信息

### fsysUpMakerObject.description

更新说明,

可以不设�?
### fsysUpMakerObject.main

主输出文�?
### fsysUpMakerObject.onCompress

```aardio aardio
fsysUpMakerObject.onCompress = function(size,outSize){
    /*开始处理文�?/
}

```

### fsysUpMakerObject.onFile

```aardio aardio
fsysUpMakerObject.onFile = function(path,size){
    /*开始处理文�?/
}

```

### fsysUpMakerObject.outDir

更新文件输出目录

### fsysUpMakerObject.updater

可选用于指定更新工具相对路�?
不指定则默认指定为main属�?
### fsysUpMakerObject.url

更新文件目录上传后的url,

必须指定该参�?
### fsysUpMakerObject.version

应用程序版本�?

不指定则自动获取

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/update/maker.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/update/maker.md')

