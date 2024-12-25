[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: gzip 读写

```aardio aardio
//gzip 读写

import zlib;

//创建只写gzip文件
gz = zlib.gzFile("/路径.gz","wb")
gz.write( {
    int data=1234; //可以压缩结构�?并写入gzip文件
    } )
gz.write("字符�?)//写入字符�?gz.close();//关闭文件句柄

//创建只读gzip文件
gz = zlib.gzFile("/路径.gz","rb")
var struct = gz.read( {
    int data=1234; //可以自gzip文件解压读取结构�?    } )
var str = gz.read(-1) //解压并读取所有字符串
gz.close();//关闭文件句柄

io.open()
io.print( struct.data,str )
execute("pause")

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/Compression/gzfile.md)

