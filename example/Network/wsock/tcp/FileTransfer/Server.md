[aardio 文档](../../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 服务�?
```aardio aardio
import console;
import wsock.tcp.server;

var tcpServer = wsock.tcp.server("127.0.0.1",7510)

console.log("服务端已启动")
tcpServer.forever(
    function(acceptSocket){

        var client = wsock.tcp.client(,acceptSocket);

        import fsys.dlg;
        var fpath = fsys.dlg.open( , "客户端连接成�?请选择文件然后开始发�?);
        if( fpath){
            var file,err = io.file(fpath,"rb") //注意 io.file 默认是文本方式读出的,b指定二进制模�?            if( file ){
                while(
                    var buf;
                    buf,readSize = file.read(1024);
                    buf
                ) {
                    client.writeBuffer(buf,readSize) ;
                }
                file.close();

                console.log("服务端发送文件完�?);
            }
        }

        client.close();
    }
)

console.log("服务端已关闭")
console.pause()

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/wsock/tcp/FileTransfer/Server.md)

