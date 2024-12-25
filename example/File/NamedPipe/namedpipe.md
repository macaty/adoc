[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 命名管道

```aardio aardio
//命名管道
import console;
import fsys.namedPipe;
console.open();

thread.invoke(
    function(){
        import console;
        import fsys.namedPipe;

        for(i=1;10;1){
            var pipeClient = fsys.namedPipe.wait("\\.\pipe\pipename")
            if( pipeClient ){
                console.log( pipeClient.read(),"线程ID" + thread.getId()  )
                pipeClient.write("线程ID" + thread.getId() + ' 服务端你好啊\r\n');
                pipeClient.close();
            }
            else {
                //其他客户端已连接,或服务端已关�?            }
        }
    }
)

thread.invoke(
    function(){
        import console;
        import fsys.namedPipe;

        for(i=1;10;1){
            var pipeClient = fsys.namedPipe.wait("\\.\pipe\pipename")
            if( pipeClient ){
                console.log( pipeClient.read(),"线程ID" + thread.getId()  )
                pipeClient.write("线程ID" + thread.getId() + ' 服务端你好啊\r\n');
                pipeClient.close();
            }
            else {
                //其他客户端已连接,或服务端已关�?            }
        }
    }
)

var count = 0;
var pipeServer = fsys.namedPipe("\\.\pipe\pipename")
while( pipeServer.connect() ){
        pipeServer.write('客户端你好\r\n')
        console.log( "服务端收到：",pipeServer.read() )
        pipeServer.disconnect();
        count++;
        if(count >=10 ) break ;
}

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/NamedPipe/namedpipe.md)

