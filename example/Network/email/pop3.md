[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: POP3 接收邮件

```aardio aardio
//POP3 接收邮件
import console;
import dotNet.MailKit;

//创建 POP3 客户�?var client = MailKit.Net.Pop3.Pop3Client()

//连接服务�?client.Connect ("pop.qq.com", 995, true)

//登录
client.Authenticate("*****@qq.com", "授权�?)

//遍历邮件
for(i=1;client.Count;1) {
    var message = client.GetMessage (i-1)
    console.log("主题:", message.Subject)
    console.log("HTML:", message.HtmlBody)
}

//断开连接
client.Disconnect(true)
console.pause()

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/email/pop3.md)

