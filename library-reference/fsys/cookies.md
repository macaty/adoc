[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.cookies 库模块帮助文�?
## fsys 成员列表

### fsys.cookies

netscape/curl cookie文件格式解析�?
### fsys.cookies()

创建netscape/curl cookie文件格式解析�?
此对象包含解析后的cookie数组,并包含以域名为键的cookie数组�?

每个cookie的字段含义如下：

domain = 域名

flag = 给定域的所有计算机是否可访问该�?
path = cookie路径

secure = cookie是否仅适用于https连接

expires = 过期时间,

这是一个time.gmt对象,RFC1123格式的时间�?
会话cookie这个字段的值为null

name = cookie名字

value = cookie的�?
[返回对象:fsyscookiesObject](#fsyscookiesObject)

## fsyscookiesObject 成员列表

### fsyscookiesObject.clear()

清空已加载的cookie

### fsyscookiesObject.get()

返回指定网址或域名的cookies,

可用参数@1指定网址,也可以用参数@1指定域名,参数@2指定网站路径

不指定网站路径时默认�?/"

### fsyscookiesObject.getCookies()

返回键值对组成的cookies字符�?可用于http请求�?失败返回null,

可用参数@1指定网址,也可以用参数@1指定域名,参数@2指定网站路径

不指定网站路径时默认�?/"

### fsyscookiesObject.header

cookie文件头描�?一般不用指�?
### fsyscookiesObject.load()

自文件加载cookie，参数指定类�?
此函数会清空之前加载的cookie

### fsyscookiesObject.mixin(\_)

混入兼容cookie数组

### fsyscookiesObject.parse()

解析多行cookie文本,参数指定字符�?
此函数会清空之前加载的cookie

### fsyscookiesObject.parseLine()

解析一行cookie文本,参数指定字符�?
此函�?不会 清空之前加载的cookie

### fsyscookiesObject.push

更新或添加cookie,参数应当是一个表,

如果指定域下已经存在同名cookie，则更新cookie

否则添加cookie

### fsyscookiesObject.push(cookie)

```aardio aardio
fsyscookiesObject.push( {
    domain = domain;
    flag  = flag;
    path = path;
    secure = secure;
    expires = ..time.gmt() ;
    name = name;
    value = value;
    httpOnly = httpOnly;
})

```

### fsyscookiesObject.save()

保存到文�?参数指定文件路径

### fsyscookiesObject.stringify()

所有cooke转换为字符串

### fsyscookiesObject.stringifyLine()

cookie转换为字符串，参数指定索�?
也可以直接传入一个cookie对象

### fsyscookiesObject.stringifySetCookieLine()

cookie转换为HTTP Set-Cookie响应头格�?

参数指定索引,也可以直接传入一个cookie对象,

可选使用参数指定前缀，不指定时默认为"Set-Cookie: ",

成功返回非空字符�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/cookies.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/cookies.md')

