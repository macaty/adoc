[aardio 鏂囨。](../../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鏈嶅姟绔?
```aardio aardio
import console;
import wsock.tcp.server;

var tcpServer = wsock.tcp.server("127.0.0.1",7510)

console.log("鏈嶅姟绔凡鍚姩")
tcpServer.forever(
    function(acceptSocket){

        var client = wsock.tcp.client(,acceptSocket);

        import fsys.dlg;
        var fpath = fsys.dlg.open( , "瀹㈡埛绔繛鎺ユ垚鍔?璇烽�夋嫨鏂囦欢鐒跺悗寮�濮嬪彂閫?);
        if( fpath){
            var file,err = io.file(fpath,"rb") //娉ㄦ剰 io.file 榛樿鏄枃鏈柟寮忚鍑虹殑,b鎸囧畾浜岃繘鍒舵ā寮?            if( file ){
                while(
                    var buf;
                    buf,readSize = file.read(1024);
                    buf
                ) {
                    client.writeBuffer(buf,readSize) ;
                }
                file.close();

                console.log("鏈嶅姟绔彂閫佹枃浠跺畬鎴?);
            }
        }

        client.close();
    }
)

console.log("鏈嶅姟绔凡鍏抽棴")
console.pause()

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/wsock/tcp/FileTransfer/Server.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 服务器报告访问的文件是隐藏的。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/wsock/tcp/FileTransfer/Server.md')

