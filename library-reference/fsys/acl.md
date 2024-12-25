[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.acl 库模块帮助文�?
## fsys.acl 成员列表

管理文件权限

当前进程需要通过管理权限启动

### fsys.acl.cacls(filePath,...)

执行 cacls 命令修改文件权限,

参数 @filePath 指定文件路径�?
可附加不定个数的字符串参数指定命令行参数,

参数 @2 也可以传入一个文本参数并用空格分隔多个命令行参数,

省略命令行参数时默认为当前登录用户添加全部权�?

失败返回 false,错误信息,成功返回进程标准输出文本

### fsys.acl.icacls(filePath,...)

执行 icacls 命令修改文件权限,

参数 @filePath 指定文件路径�?
可附加不定个数的字符串参数指定命令行参数,

参数 @2 也可以传入一个文本参数并用空格分隔多个命令行参数,

省略命令行参数时默认为当前登录用户添加全部权�?

失败返回 false,错误信息,成功返回进程标准输出文本

### fsys.acl.ownCacls(filePath,...)

执行 takeown 命令获取文件所有权�?

如果成功再执�?cacls 命令修改文件权限,

参数 @filePath 指定文件路径�?
可附加不定个数的字符串参数指定命令行参数,

省略命令行参数时默认为当前登录用户添加全部权�?

失败返回 false,错误信息,成功返回进程标准输出文本

### fsys.acl.ownICacls(filePath,...)

执行 takeown 命令获取文件所有权�?

如果成功再执行icacls命令修改文件权限,

参数 @filePath 指定文件路径�?
可附加不定个数的字符串参数指定命令行参数,

省略命令行参数时默认为当前登录用户添加全部权�?

失败返回 false,错误信息,成功返回进程标准输出文本

### fsys.acl.restore(filePath,aclPath)

执行 icacls 命令导入文件权限,

参数 @filePath 指定文件路径,

失败返回 false,错误信息,成功返回进程标准输出文本

### fsys.acl.save(filePath,aclPath)

执行 icacls 命令导出文件权限,

参数 @filePath 指定文件路径,

失败返回 false,错误信息,成功返回进程标准输出文本

### fsys.acl.takeOwn(filePath,...)

执行 takeown 命令获取文件所有权�?

参数@ filePath 指定文件路径�?
可附加不定个数的字符串参数指定命令行参数,

省略命令行参数时默认为当前登录用户获取权�?

失败返回 false ,错误信息,成功返回进程标准输出文本

### fsys.acl.takeOwnBySid(filePath,sid)

使用安全标识符获取文件或目录的所有者权�?

@sid 参数省略时默认取运行当前进程的用户SID,

这个函数由纯 aardio 代码实现，不需要调�?takeown.exe�?
可以解决XP等系统上没有 takeown.exe 的问�?
### fsys.acl.temp(filePath,proc)

```aardio aardio
fsys.acl.temp(/*指定目标文件路径�?执行 icacls 命令备份权限后调用参�?@2 指定的回调函�?
回调函数执行完自动恢复权�?
如果文件不存在，仍然会回调此函数,但回调参数为 null
成功返回回调函数的返回�?失败返回false,错误信息*/,function(filePath){

})

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/acl.md)

