[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.watch 库模块帮助文�?
## fsys 成员列表

### fsys.watch

文件监视支持�?
该对象必须在包含消息循环的线程中使用

### fsys.watch(监视路径)

参数可以是一个或多个一个或多个要监视的目录路径

也可以是包含多个目录路径的数组对�?注意不能是文件路�?
## watchObject 成员列表

### watchObject.onChange

```aardio aardio
watchObject.onChange = function(path) {
io.print("改变�? + path)  ;
return false; /*停止监视*/
}

```

### watchObject.run()

启动监控程序,

可选使用一个或多个\_FILE\_NOTIFY\_前缀常量指定临视参数,默认临视增、删、改等操�?
### watchObject.stop()

停止监视

### 自动完成常量

\_FILE\_NOTIFY\_CHANGE\_ATTRIBUTES=0x4

\_FILE\_NOTIFY\_CHANGE\_CREATION=0x40

\_FILE\_NOTIFY\_CHANGE\_DIR\_NAME=0x2

\_FILE\_NOTIFY\_CHANGE\_FILE\_NAME=0x1

\_FILE\_NOTIFY\_CHANGE\_LAST\_ACCESS=0x20

\_FILE\_NOTIFY\_CHANGE\_LAST\_WRITE=0x10

\_FILE\_NOTIFY\_CHANGE\_NORMAL\_ALL=0x5F

\_FILE\_NOTIFY\_CHANGE\_SECURITY=0x100

\_FILE\_NOTIFY\_CHANGE\_SIZE=0x8

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/watch.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/watch.md')

