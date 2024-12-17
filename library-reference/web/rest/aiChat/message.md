[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# web.rest.aiChat.message 库模块帮助文�?
## web.rest.aiChat 成员列表

### web.rest.aiChat.message()

创建 AI 聊天助手消息队列

[返回对象:webRestChatMessageObject](#webRestChatMessageObject)

## webRestChatMessageObject 成员列表

### webRestChatMessageObject.assistant(增量文本)

显示并记�?AI 接口返回的增量文本�?
参数必须是文本或者表示输出完成的 null 值�?
### webRestChatMessageObject.clear()

清除会话记录

### webRestChatMessageObject.limit

可选指定一个限制消息队列大小的数值�?
limit 限制的队列大小不包含第一个系统提示词与最后一个系统提示词�?
### webRestChatMessageObject.prompt(提示�?

添加并显示用户提示词

### webRestChatMessageObject.started()

是否已经发起对话�?
发起对话指的是消息队列中包含�?system 角色的消息�?
### webRestChatMessageObject.system(提示�?

添加并显示系统提示词

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/rest/aiChat/message.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/rest/aiChat/message.md')

