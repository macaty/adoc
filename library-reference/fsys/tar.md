[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.tar 库模块帮助文�?
## fsys 成员列表

### fsys.tar

tar文件打包

### fsys.tar("tar文件路径","打包根目�?)

参数一可以是tar文件或tar.gz文件路径,

如果省略根目录参�?打包首个文件则取其父目录为根目录

### fsys.tar()

[返回对象:fsysTarfileObject](#fsysTarfileObject)

## fsysTarfileObject 成员列表

### fsysTarfileObject.addFile("文件路径")

添加文件,

必须是指定根目录下的文件

### fsysTarfileObject.addFolder("文件路径")

添加文件,

必须是指定根目录下的子目�?
### fsysTarfileObject.close()

关闭文件

### fsysTarfileObject.onWriteDir

```aardio aardio
fsysTarfileObject.onWriteDir = function( filename ){
    /*添加目录回调函数*/
}

```

### fsysTarfileObject.onWriteFile

```aardio aardio
fsysTarfileObject.onWriteFile = function( filename ){
    /*添加目录回调函数*/
}

```

### fsysTarfileObject.onWriteFileBock

```aardio aardio
fsysTarfileObject.onWriteFileBock = function( filename,writeSize,fileSize){
    io.print( filename,writeSize,fsys.formatSize(fileSize) );/*写入文件块回调函�?/
}

```

### fsysTarfileObject.pack(目录路径,文件通配�?是否添加该目录名�?

打包目录下的所有文�?
### fsysTarfileObject.utf8

是否使用 UTF8 编码文件名�?
默认启用 UTF8 编码，建议保持默认值�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/tar.md)

