[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.remove 库模块帮助文�?
## fsys 成员列表

### fsys.remove

用于删除目录或文�?
支持 fsys.delete 函数无法删除的畸形路�?

此函数库不在 fsys 库内需要单独导�?
### fsys.remove(path)

移除参数 @1 指定路径的目录或文件

### fsys.remove(path,true)

清空参数 @1 指定路径的目录，但不删除目录本身�?
如果参数 @1 指定的不是一个存在的目录，忽略不执行任何操作

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/remove.md)

