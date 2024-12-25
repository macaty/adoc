[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.clip.file 库模块帮助文�?
## win.clip.file 成员列表

### win.clip.file.oleCopy()

清空剪贴板，然后复制文件且复�?OLE 对象�?
参数 @1 指定要复制的文件路径�?
win.clip.gif.write 函数调用了此函数复制文件

### win.clip.file.read()

返回剪贴板文件路径数�?

第二个返回值指明复制类�?复制�?copy",剪切则为"move"

### win.clip.file.write(文件路径)

将文件复制到剪贴�?
可选使用参数@3指定在复制前是否清空剪贴�?默认清空

### win.clip.file.write(文件路径,"copy")

将文件复制到剪贴�?
参数@1可用字符串或字符串数组指定一个或多个文件路径

可选使用参数@3指定在复制前是否清空剪贴�?默认清空

### win.clip.file.write(文件路径,"move")

将文件剪切到剪贴�?
参数@1可用字符串或字符串数组指定一个或多个文件路径

可选使用参数@3指定在复制前是否清空剪贴�?默认清空

### 自动完成常量

\_CF\_HDROP=0xF

\_DROPEFFECT\_COPY=1

\_DROPEFFECT\_LINK=4

\_DROPEFFECT\_MOVE=2

\_DROPEFFECT\_NONE=0

\_DROPEFFECT\_SCROLL=0x80000000

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/clip/file.md)

