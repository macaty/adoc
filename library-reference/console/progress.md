[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# console.progress 库模块帮助文�?
## console 成员列表

### console.progress()

[返回对象:ConsoleProgressObject](#ConsoleProgressObject)

### console.progress(背景字符,前景字符)

所有参数可选，默认值都设为"─"字符

## console.progress 成员列表

控制台简单进度条�?
[使用范例](../../example/Console/loading.html)

创建控制台简单进度条

### console.progress.singleLine

创建控制台简单进度条,

进度条与文本显示在同一�?
### console.progress.singleLine(宽度,背景字符,前景字符)

所有参数可选，默认值都设为"─"字符

### console.progress.singleLine(�?
[返回对象:ConsoleProgressObject](#ConsoleProgressObject)

## ConsoleProgressObject 成员列表

### ConsoleProgressObject.addProgress

增加进度

### ConsoleProgressObject.addProgress(百分�?状态文�?

百分比为0�?00的数值，状态文本为可选参�?
### ConsoleProgressObject.backColor

背景颜色,

请使用console.color下面的值指�?
### ConsoleProgressObject.backText

背景字符，默认为"─"

可以为空格，但不能为空字符串

### ConsoleProgressObject.backTextColor

背景字符颜色,

请使用console.color下面的值指�?
### ConsoleProgressObject.doneColor

进度完成后的字符颜色,

请使用console.color下面的值指�?
### ConsoleProgressObject.doneText

进度完成后的显示文本

### ConsoleProgressObject.foreColor

前景颜色,

请使用console.color下面的值指�?
### ConsoleProgressObject.foreText

前景字符，默认为"─"

可以为空格，但不能为空字符串

### ConsoleProgressObject.foreTextColor

前景字符颜色,

请使用console.color下面的值指�?
### ConsoleProgressObject.reset()

重置进度�?
如果上次进度没有完成,

要显示新的进度条前必须调用此函数

### ConsoleProgressObject.setProgress

设置进度

### ConsoleProgressObject.setProgress(百分�?状态文�?

百分比为0�?00的数值，状态文本为可选参�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/console/progress.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/console/progress.md')

