[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: stat

```aardio aardio
//端口状�?import console;
import inet.stat;

console.log("动态分配空闲端口范�?);
console.log("安装 Hyper-V 会导致动态起始端口变�?1024，并占用大量端口，导致常用端口冲�?)
execute("netsh int ipv4 show dynamicport tcp")
console.more(1);

console.log("80端口占用状�?);
console.dumpJson( inet.stat(80) );
console.more(1);

console.log("端口占用时，错误代码�?10013")
console.log("80端口占用，且进程ID�?，即 System 进程，用下面的命令查询实际服务进程ID");
execute("netsh http show servicestate")

console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/wsock/stat.md)

