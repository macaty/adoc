[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.dirWatcher 库模块帮助文�?
## fsys 成员列表

### fsys.dirWatcher("字符串参�?)

创建目录监视�?
### fsys.dirWatcher()

[返回对象:dirWatcherObject](#dirWatcherObject)

## fsys.dirWatcher 成员列表

目录监视�?
### fsys.dirWatcher.thread()

[返回对象:fsysDirWatcherThreadObject](#fsysDirWatcherThreadObject)

### fsys.dirWatcher.thread(回调函数,监视目录,选项)

```aardio aardio
fsys.dirWatcher.thread(
    function(filename,action,actionText){

    },/*监视目录路径*/ );

```

## dirWatcherEntryObject 成员列表

### dirWatcherEntryObject.action

变更类型

### dirWatcherEntryObject.actionText

变更类型说明

### dirWatcherEntryObject.filename

文件�?
### dirWatcherEntryObject.filenameW

Unicode文件�?
## dirWatcherObject 成员列表

### dirWatcherObject.close()

关闭

### dirWatcherObject.eachChanges(选项,是否监视子目�?

```aardio aardio
for( filename,action,actionText in dirWatcherObject.eachChanges() ){
    io.print( filename,actionText,action & 0x10/*_FILE_NOTIFY_CHANGE_LAST_WRITE*/ )
}

```

### dirWatcherObject.readDirectoryChanges()

[返回对象:dirWatcherEntryObject](#dirWatcherEntryObject)

### dirWatcherObject.readDirectoryChanges(选项,是否监视子目�?

读取目录发生的变�?
返回值为数组,数组成员为一个table对象

filename字段表明变更的目�?action字段表明变更类型

action�?_FILE\_NOTIFY\_CHANGE_ 前缀的常量标�?
## fsysDirWatcherThreadObject 成员列表

### fsysDirWatcherThreadObject.close()

关闭对象

### 自动完成常量

\_FILE\_ACTION\_ADDED=1

\_FILE\_ACTION\_MODIFIED=3

\_FILE\_ACTION\_REMOVED=2

\_FILE\_ACTION\_RENAMED\_NEW\_NAME=5

\_FILE\_ACTION\_RENAMED\_OLD\_NAME=4

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/dirWatcher.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/dirWatcher.md')

