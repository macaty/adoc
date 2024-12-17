[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# process.ruby.simpleHttpServer 库模块帮助文�?
## process.ruby.simpleHttpServer 成员列表

### process.ruby.simpleHttpServer.customErrors

```aardio aardio
process.ruby.simpleHttpServer.customErrors = {
    [404] = function(response){
        response.status = "404 Not Found";
        response.write("404 Not Found"); /*自定义错误页*/
    }
}

```

### process.ruby.simpleHttpServer.startIp

设置服务器端IP,

默认�?127.0.0.1"

### process.ruby.simpleHttpServer.startPort

设置服务器端�?默认自动分配空闲端口

服务端口,不指定自动分配空闲端�?
### process.ruby.simpleHttpServer.startUrl

查找可用端口创建PHP/CGI服务器，返回返回完整URL

此服务端限制使用本机IP127.0.0.1访问,并随机分配端口不会出现端口冲�?
如果Ruby/CGI服务器已启动则直接返回URL而不是重复启动服务器,

注意当前线程结束�?此服务器线程会自动退�?
### process.ruby.simpleHttpServer.startUrl(path,documentRoot,startPort)

查找可用端口创建PHP/CGI服务器，返回返回完整URL

如果PHP/CGI服务器已启动则直接返回URL而不是重复启动服务器,

省略参数返回首页URL,尾部不包含斜�?
可选用@path参数指定请求目标文件的相对路�?
可选使用参数@documentRoot指定网站根目�?默认�?/"

可选用 startPort 指定启动端口

### process.ruby.simpleHttpServer.threadNum

设置服务器线程数，默认为2个线�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/process/ruby/simpleHttpServer.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/process/ruby/simpleHttpServer.md')

