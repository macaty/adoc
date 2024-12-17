[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 瀹㈡埛绔?
```aardio aardio
//瀹㈡埛绔?import zeromq;
import console.int;

var context = zeromq.context(10)
//request妯″紡socket涓庢湇鍔＄鐨剅eply妯″紡閰嶅浣跨敤
var requester = context.zmq_socket_request() ;

requester.connect( "tcp://localhost:5559" )
if( requester.connect( "tcp://localhost:5559" ) ){
   console.log("杩炴帴鎴愬姛")
}

var msg = zeromq.message("鏈嶅姟绔綘濂?)
requester.sendMsg(msg)
msg.close();

var reply = zeromq.message()
requester.recvMsg(reply);
console.log ("瀹㈡埛绔敹鍒版秷鎭?", reply.getString() );
reply.close()

//鍏抽棴socket,涓嶇劧context.term()鏃犳硶閫�鍑?requester.close();

context.term();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/zeromq/client.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 服务器报告访问的文件是隐藏的。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/zeromq/client.md')

