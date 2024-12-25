[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Python 创建 HTTP 服务�?
```aardio aardio
//aardio 调用 Python 创建 HTTP 服务�?import console;
console.open();
console.setTitle("http.server")

import py3;
pyCode = /**
import http.server
import socketserver

Handler = http.server.SimpleHTTPRequestHandler

httpd = socketserver.TCPServer(("", 8082), Handler)

print("serving at port", 8082)
httpd.serve_forever()
**/

import process;
process.execute("http://localhost:8082")

import fsys;
fsys.setCurDir("/");//设置HTTP服务器根目录
py3.exec( pyCode );

/*
aardio 提供 wsock.tcp.simpleHttpServer, wsock.tcp.asynHttpServer 可用于创�?HTTP 服务端�?参考：aardio 范例 / Web 应用 / HTTP 服务�?*/

console.open();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/httpServer.md)

