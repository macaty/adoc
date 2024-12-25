[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.shellType 库模块帮助文�?
## fsys 成员列表

### fsys.shellType

注册文件关联

### fsys.shellType()

创建文件关联对象

fsysShellType.

## fsysShellType 成员列表

### fsysShellType.command

执行文件路径，建议指定为 io.\_exepath

### fsysShellType.contentType

文件类型。例�?"text/plain"

### fsysShellType.description

文件路径描述

### fsysShellType.documentClassName

文件类名。例�?"aardio.code.file"

### fsysShellType.extension

指定文件后缀名，字符串，不包含点号�?
### fsysShellType.icon

提供图标的文件路径。io.\_exepath

### fsysShellType.iconIndex

图标索引，例�?"1";

### fsysShellType.perceivedType

感知类型。例�?"image", "text", "audio", "compressed"

### fsysShellType.reg()

注册文件关联�?
成功返回 true，失败返�?false�?
### fsysShellType.shellNewFileName

系统菜单新建文件的文件模板路径�?
省略则不注册此项�?
### fsysShellType.unreg()

删除文件关联�?
成功返回 true，失败返�?false�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/shellType.md)

