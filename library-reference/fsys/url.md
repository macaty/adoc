[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.url 库模块帮助文�?
## fsys 成员列表

### fsys.url

网页快捷方式

### fsys.url()

创建URL快捷方式

[返回对象:urllnkObject](#urllnkObject)

## urllnkObject 成员列表

### urllnkObject.arguments

参数

### urllnkObject.description

附加说明

### urllnkObject.filename

快捷方式默认文件�?可省略后缀�?

未指定则自URL中获取文件名或域�?
### urllnkObject.getIcon()

返回图标文件路径,以及路标索引

### urllnkObject.getUrl()

返回网址

### urllnkObject.hotkey

热键

### urllnkObject.invokeCommand(verb,hwndParent)

执行指令,参数省略则打开网址

verb默认�?open"

### urllnkObject.load(url文件路径)

载入快捷方式

### urllnkObject.path

目标网址

目标路径,设置该属性时:

如果workDir为空则设workDir为目标路径所在目�?
如果description为空则设为版本信息中的文件描�?
### urllnkObject.pinToDesktop(true)

添加快捷方式到桌�?
自桌面移除快捷方�?
### urllnkObject.pinToPrograms(false,...)

自开始菜单程序组移除

可选指定多个子目录参数

如果指定了子目录则直接移除快捷方式所在父目录

### urllnkObject.pinToPrograms(true,...)

添加到开始菜单程序组

可选指定多个子目录参数

### urllnkObject.save(url文件存储路径)

保存快捷方式

如果指定了filename或path属�?参数也可以指定存储目�?
### urllnkObject.setIcon(文件路径,图标索引)

设置图标

索引可省�?默认�?

### urllnkObject.setUrl("网址")

设置网址

### urllnkObject.showCmd

显示参数

### urllnkObject.workDir

工作目录

### 自动完成常量

\_ALL\_IURL\_SETURL\_FLAGS=3

\_IURL\_SETURL\_FL\_GUESS\_PROTOCOL=1

\_IURL\_SETURL\_FL\_USE\_DEFAULT\_PROTOCOL=2

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/url.md)

