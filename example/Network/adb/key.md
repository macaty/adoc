[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 模拟按键

```aardio aardio
//模拟按键
import process.adb;
//process.adb.connect("IP:端口",true)

//发送短�?process.adb.shellGet(`am start -a android.intent.action.SENDTO -d sms:目标手机号码 --es sms_body "短信内容" --ez exit_on_sent true`)

//模拟按键
process.adb.keyDpadRight();
process.adb.keyEnter();
process.adb.keyHome()

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/adb/key.md)

