[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.knownFolder 库模块帮助文�?
## fsys 成员列表

### fsys.knownFolder(guid,path,flags,token)

返回 @guid 参数指定 GUID �?已知文件夹，

GUID 可以�?16 字节的字符串，也可以�?win.guid 支持的格式�?
可选用 @path 参数指定要拼接的子路径�?
@flags,@token 为可选参数，

用法请参�?::Shell32.SHGetKnownFolderPath 函数文档

## fsys.knownFolder 成员列表

用于获取已知的特殊文件夹

作用类似 fsys.getSpecial 函数

不支�?XP，支�?XP 以后的系�?
获取已知的特殊文件夹

### fsys.knownFolder.default(guid,path,flags)

返回默认用户�?@guid 参数指定 GUID �?已知文件夹，

参数用法�?fsys.knownFolder 相同

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/knownFolder.md)

