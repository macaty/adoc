[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# zlib.zip 库模块帮助文�?
## zlib 成员列表

### zlib.zip()

[返回对象:zlibZipObject](#zlibZipObject)

### zlib.zip(zip路径,根目�?是否追加)

创建压缩文件对象�?
参数�?参数三都可以省略�?
如果不指定根目录，首先调�?compress 函数时将自动指定�?
如果首次压缩的是目录，则该目录设为根目录，否则文件的父目录设为根目录�?
## zlibZipObject 成员列表

### zlibZipObject.beginWrite(文件路径,压缩密码,压缩级别)

开始添加压缩文�?

密码为可选参�?压缩级别可省�?默认�?

### zlibZipObject.close()

关闭对象

### zlibZipObject.compress(压缩源目�?回调函数,压缩密码,压缩级别,缓冲区大�?

```aardio aardio
zlibZipObject.compress( "/*源目�?/",
    function(len,path){
        ..io.print( len,path )
    }
)

```

### zlibZipObject.endWrite()

添加压缩文件完成

### zlibZipObject.writeBuffer(buffer,长度)

参数@1 使用 raw.buffer 函数分配�?buffer 对象,

长度可省�?
### zlibZipObject.writeDir(目录路径)

添加目录

### 自动完成常量

\_ZIP\_BADZIPFILE=-103

\_ZIP\_EOF=0

\_ZIP\_ERRNO=-1

\_ZIP\_INTERNALERROR=-104

\_ZIP\_OK=0

\_ZIP\_PARAMERROR=-102

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/zlib/zip.md)

