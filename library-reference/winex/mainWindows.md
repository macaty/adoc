[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# winex.mainWindows 库模块帮助文�?
## winex 成员列表

### winex.mainWindows("EXE文件�?,true)

查找并等待指�?EXE 运行进程的所有主窗口显示�?
返回表的键为进程 ID，值为包含窗口信息的表�?
窗口信息的字段：

hwnd 字段为窗口句柄�?
title 字段为窗口标题�?
其他字段与无参数调用此函数的返回值相�?
### winex.mainWindows()

无参数则返回所有可以找到主窗口的进程表�?
返回表的键为进程 ID，值为包含窗口信息的表�?
窗口信息的字段：

hwnd 字段为窗口句柄�?
title 字段为窗口标题�?
threadId 字段为窗口线�?ID�?
visible 字段为是否可见�?
main 字段为是否无所有者窗�?
### winex.mainWindows(进程)

如果参数@1传入进程ID�?process 对象�?
找到则返回包含主窗口信息的表对象�?
其中 hwnd 字段为窗口句柄，title 字段为窗口标题�?
找不到则返回 null

### winex.mainWindows(进程,true)

查找并等待进程显示主窗口�?
参数@1传入进程ID�?process 对象�?
返回包含主窗口信息的表对象�?
其中 hwnd 字段为窗口句柄，title 字段为窗口标�?
## winex.mainWindows 成员列表

用于查找进程主窗口�?
如果进程有多个窗口，

则优先取无父窗口及无所有者的可见窗口，并优先取非空标题窗口�?
### winex.mainWindows.each("EXE文件�?,true)

```aardio aardio
for i,hwnd,title,visible,pid,tid in winex.mainWindows.each("EXE文件�?,true){
    /*等待指定 EXE 运行进程的所主窗口显示，然后遍历这些主窗口�?迭代器返回参数依次为�?序号，窗口句柄，标题，是否显示，进程ID，线程ID*/
}

```

### winex.mainWindows.each()

```aardio aardio
for i,hwnd,title,visible,pid,tid in winex.mainWindows.each(){
    /*遍历所有主窗口�?迭代器返回参数依次为�?序号，窗口句柄，标题，是否显示，进程ID，线程ID*/
}

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/winex/mainWindows.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/winex/mainWindows.md')

