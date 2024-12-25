[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: gzip 解压网页

```aardio aardio
//gzip 解压网页

/*
如果已导入zlib�?解压gzip格式的网页需要用�?zlib.gzCompress 函数),
inet.http,inet.whttp 在readAll() get() post() 等一次读取全部下载数据的函数中支持自动解压gzip格式数据�?web.res.client以及继承自web.res.client的库因为使用 inet.http ，所以同样可以导入zlib支持gzip解压�?
因为并不是所有程序都一定需�?zlib模块，所以请自行决定是需要添�?import zlib;
*/

import zlib;
import inet.http;

import console;
console.log("正在下载gzip数据")

var http = inet.http();

/*
服务器并不一定理�?Accept-Encoding,
客户端仍然要在响应HTTP头中读取 Content-Encoding 的值判断返回的压缩格式�?*/
var str = http.get("http://eu.httpbin.org/gzip","Accept-Encoding:gzip");
//注意Accept-Encoding:deflate 在服务端、客户端兼容性都不好,一般不会使�?
console.log(str);
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/Compression/gzip.md)

