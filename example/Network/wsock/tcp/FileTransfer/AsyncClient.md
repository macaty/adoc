[aardio 文档](../../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 异步非阻塞客户端

```aardio aardio
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=660;bottom=381)
winform.add(
edit={cls="edit";left=19;top=14;right=641;bottom=363;edge=1;multiline=1;z=1}
)
/*}}*/

import wsock.tcp.asynClient;
var tcpClient = wsock.tcp.asynClient();

var file = io.file("/test.zip","w+b");//注意 io.file 默认是文本方式写入的,b指定二进制模�?
/*
recv,recvBuffer函数�?read前缀的读数据函数有所区别�?recv不保证每次一定会读完数据，所以在onClose事件里要一直读到没有任何数据�?
onReceive里不能多次调用recv，如果希望每次都把接收缓冲区中的数据读完�?请在 onRead事件中调用read前缀的系列函数接收数据�?*/
var buffer = raw.buffer(0x100000);
tcpClient.onReceive = function(err){

    var readSize = tcpClient.recvBuffer(buffer);

    if( readSize ) {
        file.writeBuffer(buffer,readSize);
        winform.edit.log("已下�?,math.size64( file.seek() ).format(),'\r\n')
    }
}

//如果用recv,recvBuffer函数收取数据，必须在onClose事件中继续收取最后的数据
tcpClient.onClose = function(err){
    for(readSize,remainSize in tcpClient.eachReadBuffer(buffer) ){
        file.writeBuffer(buffer,readSize);
        winform.edit.log("已下�?,math.size64( file.seek() ).format(),'\r\n')
    }
    winform.edit.log("服务端已断开",err);
}

tcpClient.connect("127.0.0.1",7510) //因为是异步套接字,这里不需要检查返回�?
winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/wsock/tcp/FileTransfer/AsyncClient.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/wsock/tcp/FileTransfer/AsyncClient.md')

