[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.caseSensitivity 库模块帮助文�?
## fsys.caseSensitivity 成员列表

用于获取或设置指定目录下路径是否分区大小�?
### fsys.caseSensitivity.get(dirPath)

指定目录下路径是否分区大小写,

@dirPath 参数指定目录路径

区分大小写返�?true，不区分返回 false�?
发生错误返回 null,错误代码

错误代码参�?错误代码参�?[https://docs.microsoft.com/en-us/openspecs/windows\_protocols/ms-erref/596a1078-e883-4972-9bbc-49e60bebca55](https://docs.microsoft.com/en-us/openspecs/windows_protocols/ms-erref/596a1078-e883-4972-9bbc-49e60bebca55)

### fsys.caseSensitivity.get(dirPath,enabled)

设置指定目录下路径是否分区大小写,

@dirPath 参数指定目录路径,@enabled 指定是否区分大小�?
成功返回 true,发生错误返回 null,错误代码�?
常见错误代码�?
0xC0000022 进程需要管理权�?
0xC000000D 参数错误

0xC00000BB 不支持，需要安�?WSL（Windows Subsystem for Linux�?
### fsys.caseSensitivity.getName()

获取参数@1指定路径的大小写敏感的文件名�?
参数支持文件搜索通配符（�?fsys.enum 相同）�?
此函数不需要系统安�?WSL

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/caseSensitivity.md)

