[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: AI 聊天简�?
```aardio aardio
//AI 聊天简�?
import console;

import web.rest.aiChat;

//创建 Anthropic �?OpenAI 兼容 AI 聊天接口
var ai = web.rest.aiChat(
    //下面的测试密�?24 小时后失效，DeepSeek �?key �?10 元估计能用一年，请自己申请一个吧�?    key = "sk-2f729981180a45e3b28971e9a5c68c72";
    url = "https://api.deepseek.com/v1";//接口地址
    model = "deepseek-chat";//模型名称首字符为 @ 则使�?Anthropic 接口
    temperature = 0.1;//温度
    maxTokens = 1024,//最大回复长�?)

//创建 AI 会话消息队列
import web.rest.aiChat.message;
var msg = web.rest.aiChat.message();

//添加系统提示�?msg.system("你是 aardio 编程助手�?);
while( var txt = console.getText( "请输入问�?" ) ) {

    //添加用户提示�?    msg.prompt(txt);

    //调用聊天接口，回调参�?2 指定�?console.writeText 输出 AI 回复的增量文本�?    var ok,err = ai.messages(msg,console.writeText);
    if(err) console.error(err)

    console.print('\n-----------------------------\n');
}

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/REST/aiChatCon.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/REST/aiChatCon.md')

