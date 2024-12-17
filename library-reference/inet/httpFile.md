[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# inet.httpFile 库模块帮助文�?
## inet 成员列表

### inet.httpFile

下载文件,支持断点续传

### inet.httpFile()

[返回对象:inetFileObject](#inetFileObject)

### inet.httpFile(URL,存储路径,配置文件路径,userAgent,proxy,...)

存储路径如果是目录则必须以反斜杠结尾,

存储路径如果是目录或者未指定后缀�?则尝试自动获取文件名

配置文件可指定目�?也可以是文件路径（必须指定后缀名）

如果不指定配置文件路�?则指定为存储路径 \+ ".dow!oad"

其他可选参数用于创建http对象,参考inet.http构造函数说�?
## inetFileObject 成员列表

### inetFileObject.bufferSize

缓冲区大�?
不指定则默认�?28KB

### inetFileObject.close()

关闭连接

### inetFileObject.complete

是否下载完成

### inetFileObject.contentLength

需要下载的文件长度

如果文件长度为零,并且modified属性为false,表示不需要重新下�?
download函数返回值为 true �?contentLength 表示已下载文件总长�?
### inetFileObject.download(HTTP�?引用网址,accept,flags,postData)

下载文件,所有参数都是可选参�?

下载成功返回true,

文件已下载成功无需重新下载返回true,错误信息,

下载失败返回null以及错误信息

取消返回false,无错误信�?
可通过complete属性检测本次下载文件是否成�?
### inetFileObject.filename

存储文件�?

仅在存储路径为目录时有效,

可在调用download函数以前修改,

如果未指定则在调�?test �?download 函数时自动获�?
### inetFileObject.isModified()

检测已下载的文件在服务器上是否已被修改,

该函数会调用 download() 进行测试(不会启动下载)

### inetFileObject.modified

文件是否己更�?
### inetFileObject.onReceive

```aardio aardio
inetFileObject.onReceive = function(buffer,readSize,contentLength){

}

```

### inetFileObject.onReceiveBegin

```aardio aardio
inetFileObject.onReceiveBegin = function(statusCode,contentLength,fileSize){
    if( statusCode == 206/*断点续传*/ ){

    }
}

```

### inetFileObject.path

存储路径,

可在调用download函数以前修改

### inetFileObject.removeResumeFile()

移除断点续传配置文件

### inetFileObject.resumePath

续传文件路径,

可在调用download函数以前修改

### inetFileObject.session

HTTP连接对象

[返回对象:inetHttpObject](#inetHttpObject)

### inetFileObject.statusCode

HTTP状态码

### inetFileObject.test(HTTP�?引用网址,accept,flags,postData)

检测是否已下载最新文�?
已下载文件未变更返回true

需要下载或续传返回false,下载错误返回null以及错误信息

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/inet/httpFile.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/inet/httpFile.md')

