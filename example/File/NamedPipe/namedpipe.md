[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鍛藉悕绠￠亾

```aardio aardio
//鍛藉悕绠￠亾
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
                console.log( pipeClient.read(),"绾跨▼ID" + thread.getId()  )
                pipeClient.write("绾跨▼ID" + thread.getId() + ' 鏈嶅姟绔綘濂藉晩\r\n');
                pipeClient.close();
            }
            else {
                //鍏朵粬瀹㈡埛绔凡杩炴帴,鎴栨湇鍔＄宸插叧闂?            }
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
                console.log( pipeClient.read(),"绾跨▼ID" + thread.getId()  )
                pipeClient.write("绾跨▼ID" + thread.getId() + ' 鏈嶅姟绔綘濂藉晩\r\n');
                pipeClient.close();
            }
            else {
                //鍏朵粬瀹㈡埛绔凡杩炴帴,鎴栨湇鍔＄宸插叧闂?            }
        }
    }
)

var count = 0;
var pipeServer = fsys.namedPipe("\\.\pipe\pipename")
while( pipeServer.connect() ){
        pipeServer.write('瀹㈡埛绔綘濂絓r\n')
        console.log( "鏈嶅姟绔敹鍒帮細",pipeServer.read() )
        pipeServer.disconnect();
        count++;
        if(count >=10 ) break ;
}

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/NamedPipe/namedpipe.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/NamedPipe/namedpipe.md')

