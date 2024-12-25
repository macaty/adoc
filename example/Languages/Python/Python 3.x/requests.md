[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Python 如何指定命名参数

```aardio aardio
//aardio 调用 Python 如何指定命名参数
import console;
import py3;

var requests = py3.import("requests");
var ses = requests.Session();

/*
pyObject.$method() 等价�?pyObject.method.invoke() �?
如果 pyObject.method.invoke( kwargs ) 的第一个参�?@kwargs 是表对象�?则表中的名值对用于指定命名参数，其他数组成员作为匿名参数按索引顺序传给 Python 函数�?
@kwargs 参数如果是表，且『先写名值对』，�?aardio 中就可以省略外层�?{}�?*/
var res = ses.$get(verify=false,"https://www.aardio.com");

console.log( res.text );
/*
如果开全局代理，Python 可能会报错（SSLEOFError），
这个问题�?Python 的问题与 aardio 无关，解决方案请自行上网搜索�?
改用 aardio 中的 inet.http �?web.rest.client 可自动支持全局代理�?*/

console.pause()

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/requests.md)

