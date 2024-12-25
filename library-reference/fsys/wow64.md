[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.wow64 库模块帮助文�?
## fsys.wow64 成员列表

64 位文件与注册表重定位管理

### fsys.wow64.disableRedirection( 回调函数 )

```aardio aardio
fsys.wow64.disableRedirection(
    function(){
        /*如果运行�?4位暂时禁用文件与注册表重定向
此函数兼�?2位系�?返回回调函数的首个返回�?/
    }
)

```

### fsys.wow64.disableRedirectionEx( 回调函数 )

返回一个调用回调函数并与回调函数拥有相同功能的新函�?

执行返回函数时禁用文件与注册表重定向

### fsys.wow64.process

禁用64位文件重定向并运行执行文件或关联文档，兼�?2位系�?

失败则返�?null,错误信息,错误代码

成功返回进程对象

### fsys.wow64.process( ,系统命令�?

如果省略第一个参�?并仅指定命令�?则作为系统命令行启动运行

### fsys.wow64.process()

[返回对象:processObject](https://www.aardio.com/zh-cn/doc/library-reference/process/_.html#processObject)

### fsys.wow64.process(执行文件,参数,STARTUPINFO)

STARTUPINFO 参数�?process.STARTUPINFO 结构�?可选参�?
如果该参数是普�?table 对象.将自动创建为 STARTUPINFO 结构�?
### fsys.wow64.process(执行文件,命令行参�?更多命令行参�?...)

命令行参数可以是一个数组或多个字符串参�?
如果命令行参数有多个,则以空格分隔自动合并,

合并时遇到需要转义的参数则进行转义处理并且首尾添加双引号

首尾已经有引号的参数不作转义处理,

命令参数最大长度为8191/0x1FFFF个字�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/wow64.md)

