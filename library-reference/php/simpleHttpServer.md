[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# php.simpleHttpServer 库模块帮助文�?
## php.simpleHttpServer 成员列表

调用 process.php.simpleHttpServer �?CGI 方式启动 PHP,

php-cgi.exe 路径默认指定�?"~\\lib\\php.dll\\php-cgi.exe";

### php.simpleHttpServer.startUrl

查找可用端口创建PHP/CGI服务器，返回返回完整URL

此服务端限制使用本机IP127.0.0.1访问,并随机分配端口不会出现端口冲�?
如果PHP/CGI服务器已启动则直接返回URL而不是重复启动服务器,

注意当前线程结束�?此服务器线程会自动退�?
### php.simpleHttpServer.startUrl(path,documentRoot)

查找可用端口创建PHP/CGI服务器，返回返回完整URL

如果PHP/CGI服务器已启动则直接返回URL而不是重复启动服务器,

省略参数返回首页URL,尾部不包含斜�?
可选用@path参数指定请求目标文件的相对路�?
可选使用参数@documentRoot指定网站根目�?默认�?/"

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/php/simpleHttpServer.md)

