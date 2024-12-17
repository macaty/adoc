[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 Python 鍒涘缓 HTTP 鏈嶅姟鍣?
```aardio aardio
//aardio 璋冪敤 Python 鍒涘缓 HTTP 鏈嶅姟鍣?import console;
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
fsys.setCurDir("/");//璁剧疆HTTP鏈嶅姟鍣ㄦ牴鐩綍
py3.exec( pyCode );

/*
aardio 鎻愪緵 wsock.tcp.simpleHttpServer, wsock.tcp.asynHttpServer 鍙敤浜庡垱寤?HTTP 鏈嶅姟绔�?鍙傝�冿細aardio 鑼冧緥 / Web 搴旂敤 / HTTP 鏈嶅姟鍣?*/

console.open();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/httpServer.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/httpServer.md')

