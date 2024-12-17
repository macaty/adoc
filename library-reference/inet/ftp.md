[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# inet.ftp 库模块帮助文�?
## inet 成员列表

### inet.ftp()

[返回对象:inetFtpObject](#inetFtpObject)

### inet.ftp(主机,用户�?密码,端口�?是否被动模式,UserAgent,代理,绕过代理,选项)

除第一个参数以�?其他参数可�?
## inet.ftp 成员列表

FTP文件传输支持�?
### inet.ftp.getParentDir(路径)

返回父目�?
## ftpFileObject 成员列表

### ftpFileObject.close()

关闭FTP文件

### ftpFileObject.eachRead(缓冲区长�?

```aardio aardio
for(str in ftpFileObject.eachRead() ){

}

```

### ftpFileObject.eachReadBuffer

```aardio aardio
var buffer = ..raw.buffer( 1024 * 10 );
for( size in ftpFileObject.eachReadBuffer( buffer ) ){
    table.push(,str ) ;
}

```

### ftpFileObject.read()

读文�?返回文件数据,

可选指定缓冲区长度

### ftpFileObject.read(-1)

读取所有数�?
### ftpFileObject.readBuffer(buffer,写入长度)

下载文件数据

参数一必须是使�?buffer 对象

长度参数可�?默认为缓冲区长度.

### ftpFileObject.size()

返回文件大小

### ftpFileObject.size64()

返回文件大小

返回文件大小

返回值为math.size64长整数对�?
[返回对象:mathSize64Object](../math/_.html#mathSize64Object)

### ftpFileObject.write(写入字符�?不定个数字符�?

写文�?支持多参�?

返回写入数据的总长�?失败返回空或0

### ftpFileObject.writeBuffer(buffer,写入长度)

上传文件数据

参数一必须是使�?buffer 对象

长度参数可�?默认为缓冲区长度.

## inetFtpObject 成员列表

### inetFtpObject.close()

关闭连接

### inetFtpObject.command("OPTS UTF8 off")

发送命令通知服务器关闭UTF8编码模式

可解决中文文件名乱码问题

### inetFtpObject.command(命令,选项,是否返回句柄)

仅指定第一个参数即�?

参数2指定传送模�?默认为BINARY模式

也可指定为\_INTERNET\_FLAG\_TRANSFER\_ASCII

参数3默认为false,如果为true则第二个返回值为返回句柄

### inetFtpObject.createDir(目录)

创建目录,支持创建多级目录

可以斜杠开头的的路径表示相对于根目录的完整路径

也可使用setCurDir()设定当前目录

### inetFtpObject.createParentDir(目录)

创建指定路径的父目录

### inetFtpObject.delete(文件)

删除文件

### inetFtpObject.deleteDir(目录)

删除目录

### inetFtpObject.download("/本地路径","/远程路径")

下载前可使用setCurDir()设定当前目录

也可以斜杠开头的的路径表示相对于根目录的完整路径

### inetFtpObject.download(loadfile,remotefile,1/\*\_INTERNET\_FLAG\_TRANSFER\_ASCII\*/)

ASCII模式下载

### inetFtpObject.download(loadfile,remotefile,2/\*\_INTERNET\_FLAG\_TRANSFER\_BINARY\*/)

BINARY模式下载

### inetFtpObject.eachDir

```aardio aardio
for(dirName,fileName,findData,curDir in inetFtpObject.eachDir("\")){
     if( !fileName ){
        io.print("目录�?,dirName);
     }
     else{
        io.print("文件�?,fileName);
     }
     /*curDir为当前目�?如果当前是一个文件请忽略dirName参数
如果当前是一个目�?fileName为空*/
}

```

### inetFtpObject.enumDir(目录,通配�?回调函数)

```aardio aardio
inetFtpObject.enumDir("\","*.*",
    function(dir,fileName,fullpath,findData ){
        io.print( fileName?"文件":"目录",fullpath )
        return true;/*返回false停止*/
    }
);

```

### inetFtpObject.getCurDir()

返回服务器上的当前目�?该函数保证返回的目录尾部是斜�?
### inetFtpObject.open("/目录/文件路径","rb")

二进制只读模式打开ftp文件�?
参数2�?rt"则使用文本模�?

打开文件后仅允许读文�?其他所有FTP操作被禁�?

直到调用close()关闭文件

### inetFtpObject.open("/目录/文件路径","wb")

二进制只写模式打开ftp文件�?
参数2�?wt"则使用文本模�?

打开文件后仅允许写文�?其他所有FTP操作被禁�?

直到调用close()关闭文件

### inetFtpObject.open()

[返回对象:ftpFileObject](#ftpFileObject)

### inetFtpObject.rename(文件�?新名�?

文件改名

### inetFtpObject.setCurDir(目录)

设置服务器上的当前目�?
### inetFtpObject.upload("/本地路径","远程路径")

上传前可使用setCurDir()设定当前目录

也可以斜杠开头的的路径表示相对于根目录的完整路径

### inetFtpObject.upload(formfile,todir,1/\*\_INTERNET\_FLAG\_TRANSFER\_ASCII\*/)

ASCII模式上传

### inetFtpObject.upload(formfile,todir,2/\*\_INTERNET\_FLAG\_TRANSFER\_BINARY\*/)

BINARY模式上传

### 自动完成常量

\_FTP\_TRANSFER\_TYPE\_ASCII=1

\_FTP\_TRANSFER\_TYPE\_BINARY=2

\_INTERNET\_FLAG\_TRANSFER\_ASCII=1

\_INTERNET\_FLAG\_TRANSFER\_BINARY=2

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/inet/ftp.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/inet/ftp.md')

