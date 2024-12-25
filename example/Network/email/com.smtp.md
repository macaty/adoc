[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: com.smtp 发送邮�?
```aardio aardio
//com.smtp 发送邮�?import console;
import com.smtp;

var smtp = com.smtp();

smtp.from="1000@qq.com" //发件�?smtp.to="1000@qq.com" //收件�?smtp.ssl = true;

smtp.server="smtp.qq.com" //邮件服务�?smtp.username="1000@qq.com" //用户�?smtp.password = "1000100010001000" //密码
smtp.subject="标题" //邮件标题
smtp.html="邮件内容" //邮件内容

io.open()
try{
    console.log("正在发送邮�?..")
    smtp.send();//发送邮�?}
catch(e){
    console.log("出错�?请正确设置smtp服务器登录信�?如密码等.",e)
}

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/email/com.smtp.md)

