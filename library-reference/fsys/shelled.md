[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.shelled 库模块帮助文�?
## fsys.shelled 成员列表

### fsys.shelled.folderIds()

返回一个数�?

数组中包含所�?所�?Shell 文件�?CLSID �?名称组成的数�?
### fsys.shelled.lock

设置为保护目�?
### fsys.shelled.lock(path,shellFolderId)

设置为保护目录�?
成功返回保护目录路径，失败返�?null�?
@path 指定设为保护目录之前的原始路�?@shellId 指定 Shell 文件�?CLSID

### fsys.shelled.unlock

取消设置为保护目录�?
成功返回恢复后的目录路径，失败返�?null�?
### fsys.shelled.unlock(path,shellFolderId)

取消设置为保护目录�?
成功返回恢复后的目录路径，失败返�?null�?
@path 指定设为保护目录之前的原始路�?@shellId 指定 Shell 文件�?CLSID

### fsys.shelled.unlock(shelledPath)

取消设置为保护目录�?
成功返回恢复后的目录路径，失败返�?null�?
@shelledPath 指定保护目录路径

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/shelled.md)

