[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: IMAP 接收邮件

```aardio aardio
//IMAP 接收邮件
import console;
import dotNet.MailKit;

//创建 IMAP 客户�?var client = MailKit.Net.Imap.ImapClient()

//连接�?IMAP 服务�?client.Connect("imap.qq.com", 993, true)

//登录
client.Authenticate("*****@qq.com", "授权�?)

//打开收件�?var inbox = client.Inbox;
inbox.Open(MailKit.FolderAccess.ReadOnly)

//获取最�?10 封邮�?for(i=inbox.Count;math.max(1,inbox.Count-9);-1){
    var message = inbox.GetMessage(i-1);
    console.log("主题:", message.Subject)

    console.log("发件�?", message.From)
    console.log("日期:", message.Date)
    console.log("------------------------")

    //HTML格式邮件内容
    console.log("HTML:", message.HtmlBody)

}

//断开连接
client.Disconnect(true)

console.pause()

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/email/imap.md)

