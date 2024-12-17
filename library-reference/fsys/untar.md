[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.untar 库模块帮助文�?
## fsys 成员列表

### fsys.untar

tar文件操作

### fsys.untar("tar文件路径",存储路径)

参数@1可以�?\*.tar, \*.tar.gz, \*.tgz 类型文件路径,

参数 @1 也可以指�?fsys.stream �?fsys.file,io.file 等文件对�?

如果参数@1为文件路�?则参数@2为可选参�?
### fsys.untar()

[返回对象:fsysUntarfileObject](#fsysUntarfileObject)

## fsysUntarfileObject 成员列表

### fsysUntarfileObject.blocksCount

数据块总数,

仅供进度条使用的估算�?
### fsysUntarfileObject.close()

关闭文件,

如果解包完成返回true

### fsysUntarfileObject.complete

所有文件是否解包完�?
### fsysUntarfileObject.eachBlock(posRange)

```aardio aardio
for(fileName,writeSize,remainSize,pos in fsysUntarfileObject.eachBlock() ){
     /*循环展开所有文件块,
文件块较多时指定posRange参数可以减少循环次数以优化性能
posRange参数可选指定一个表示进度上限的数�?
指定posRange参数则返回值pos表示当前进度*/
}

```

### fsysUntarfileObject.lastError

调用eachBlock解包时，可使用lastError获取错误信息

### fsysUntarfileObject.nextBlock()

释放下一个块,

成功返回文件�?释放大小,

同一文件可能需要释放多个文件块

### fsysUntarfileObject.onProgressFile

```aardio aardio
fsysUntarfileObject.onProgressFile = function(path){
    /*正在创建文件*/
}

```

### fsysUntarfileObject.onProgressFolder

```aardio aardio
fsysUntarfileObject.onProgressFolder = function(path){
    /*正在创建目录*/
}

```

### fsysUntarfileObject.utf8

tar 文件名是否使�?UTF8 编码�?
设为 false ，表示文件名使用 ANSI 多字节编码�?
设为 true 表示文件名使�?utf8 编码,

设为 null 则自动检测�?
目前 tar 文件一般使�?UTF-8 编码文件名，使用 ANSI 编码不常见�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/untar.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/untar.md')

