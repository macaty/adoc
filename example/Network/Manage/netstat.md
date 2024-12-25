[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 端口状�?
```aardio aardio
//端口状�?import console.int;
import inet.stat;

//列出 UDP 连接
console.dump(inet.stat().udp)

//列出 80 端口�?TCP 连接
console.dump(inet.stat(80).tcp)

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/Manage/netstat.md)

