[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# zlib.unzip 库模块帮助文�?
## zlib 成员列表

### zlib.unzip()

[返回对象:unzipObject](#unzipObject)

### zlib.unzip(zip路径)

创建解压对象

注意如果zip文件为空返回null

zip路径错误则抛出异�?调用者有责任检测路径是否正�?
## zlib.unzip 成员列表

### zlib.unzip.extract(zip文件路径,解压目录,筛选函�?解压密码)

```aardio aardio
zlib.unzip.extract( "/my.zip","/my",
    function(fileName,extractPath,fileInfo,size,unitSize,unitName){
        if(extractPath){
            return true/*是否解压该文�?/;
        }
    }, ,
    function(numEntries){

    }
)

```

## unzFileInfoObject 成员列表

### unzFileInfoObject.compressed\_size

压缩大小

### unzFileInfoObject.compressed\_size\_high

压缩大小,高位

### unzFileInfoObject.crc

原始文件CRC32校验�?允许负整�?

### unzFileInfoObject.dosDate

DOS时间格式

### unzFileInfoObject.flag

选项

### unzFileInfoObject.uncompressed\_size

原始大小

### unzFileInfoObject.uncompressed\_size\_high

原始大小,高位

## unzipObject 成员列表

### unzipObject.codepage

指定zip文件名使用的代码�?数�?
### unzipObject.eachFile( )

```aardio aardio
for(pos,dirName,fileName,extractPath,fileInfo in unzipObject.eachFile() ){
    if( dirName ) continue;

    var file = io.file( extractPath,"w+b" )
    for(buffer,readSize in unzipObject.eachReadCurrentFile() ){
        file.writeBuffer(buffer,readSize);
    }
    file.close();
}

```

### unzipObject.eachFile()

[返回对象:unzFileInfoObject](#unzFileInfoObject)

### unzipObject.eachReadCurrentFile(解压密码,缓冲区大�?

```aardio aardio
for(buffer,readSize in unzipObject.eachReadCurrentFile() ){
    file.writeBuffer(buffer,readSize);
}

```

### unzipObject.globalInfo.number\_entry

文件与目录总数

### 自动完成常量

\_UNZ\_BADZIPFILE=-103

\_UNZ\_CRCERROR=-105

\_UNZ\_END\_OF\_LIST\_OF\_FILE=-100

\_UNZ\_EOF=0

\_UNZ\_ERRNO=-1

\_UNZ\_INTERNALERROR=-104

\_UNZ\_OK=0

\_UNZ\_PARAMERROR=-102

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/zlib/unzip.md)

