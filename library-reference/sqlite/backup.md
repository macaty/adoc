[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sqlite.backup 库模块帮助文�?
## sqlite 成员列表

### sqlite.backup

创建数据库备份对�?
因为sqlite可以有不同版本的替换实现,

所以请在导入sqlite.backup以前必须先导入sqlite支持�?

### sqlite.backup()

[返回对象:sqlitBackupObject](#sqlitBackupObject)

### sqlite.backup(src,dst,srcName,dstName)

创建数据库备份对�?
src指定源数据库,可以是一个sqlite数据库对�?也可以指定要打开的数据库路径

dst指定输出数据�?可以是一个sqlite数据库对�?也可以指定要打开的数据库路径

srcName为源数据库名,dstName为目的数据库�?
数据库名字一般不用指�?默认�?main",也就是主数据�?
## sqlitBackupObject 成员列表

### sqlitBackupObject.count()

需要备份的总页�?
### sqlitBackupObject.eachStep(1)

```aardio aardio
for remaining,count in sqlitBackupObject.eachStep(1) {
    /*用于for in语句中执行备份操作的迭代�?参数指定每次迭代备份的页�?不指定时默认�?
迭代变量remaining为剩余的页数,count为总页�?备份完成退出循环并调用finish函数释放资源
其他数据库错误会抛出异常*/
}

```

### sqlitBackupObject.finish()

释放备份对象

### sqlitBackupObject.remaining()

当前剩余的页�?
### sqlitBackupObject.step()

执行备份操作

可选在参数中指定页�?

指定为负数或者不指定则默认备份所有数�?
返回成功返回0,备份完成返回101,也就是sqlite.DONE

其他数据库错误会抛出异常

在备份完成后自动调用finish函数释放资源

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/sqlite/backup.md)

