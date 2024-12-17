[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.form.chat 库模块帮助文�?
## web.form 成员列表

### web.form.chat

用于显示 Markdown 生成�?HTML �?AI 助手专用 web 窗体�?
此对象继承自 web.form.simpleMarkdown �?web.form 对象�?
创建用于显示 Markdown 生成�?HTML �?AI 助手专用 web 窗体�?
此对象继承自 web.form.simpleMarkdown �?web.form 对象�?
### web.form.chat()

[返回对象:webFormChatObject](#webFormChatObject)

### web.form.chat(winform,hostFlags,dlControl,userAgent,securityTrusted)

创建 Web 窗体�?
winform 必须指定窗体�?custom 控件�?
其他参数不必指定，这些参数的用法请参�?web.form �?
## webFormChatObject 成员列表

### webFormChatObject.assistant(增量文本)

显示并记�?AI 接口返回的增量文本�?
参数必须是文本或者表示输出完成的 null 值�?
### webFormChatObject.beforerWriteEnd

```aardio aardio
webFormChatObject.beforerWriteEnd = function(markdown){
    /*在输出完整回复以前，可在此回调中修改返回输出的全�?Markdown�?错误输出不会触发此函数�?/
}

```

### webFormChatObject.clear()

清除会话记录

### webFormChatObject.errorMessage(错误信息)

显示错误信息

### webFormChatObject.getMarkdown()

返回输出到页面的所�?Markdown 格式内容�?
### webFormChatObject.lastAssistantMessage()

AI 最后一次返回的消息，如果没有则返回 null�?
### webFormChatObject.lastMarkdown()

获取最后一�?AI 回复的原�?Markdown 格式内容�?
### webFormChatObject.onWriteEnd

```aardio aardio
webFormChatObject.onWriteEnd = function(){
    /*发出问题以后，AI 回复完成或出现错误回调此事件*/
}

```

### webFormChatObject.prompt(提示�?

添加并显示用户提示词

### webFormChatObject.setMarkdown()

输出 Markdown 格式内容到页面，覆盖控件存储�?Markdown�?
### webFormChatObject.showLoading(title)

显示加载动画，可选用 title 指定标题�?
### webFormChatObject.started()

是否已经发起对话�?
发起对话指的是消息队列中包含�?system 角色的消息�?
### webFormChatObject.system(提示�?

添加并显示系统提示词

### webFormChatObject.write()

清空页面内容，解析并显示参数 @1 指定�?Markdown 为网页�?
控件仅解析与显示 Markdown，不会存储此 Markdown�?
也不会改�?getMarkdown 函数的返回值�?
### webFormChatObject.writeDelta()

向页面追�?Markdown 格式内容�?
解析、显示、并存储写入�?Markdown�?
## webFormChatObject.chatMessage 成员列表

消息队列，用于发送到 chat/completions 聊天接口�?
### webFormChatObject.chatMessage.limit

可选指定一个限制消息队列大小的数值�?
limit 限制的队列大小不包含第一个系统提示词与最后一次抓取网址后发送的知识库�?
但其他通过抓取网址发送的知识库消息会计算在内（在页面上不显示）�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/form/chat.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/form/chat.md')

