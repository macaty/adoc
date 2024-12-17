[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.lnk 库模块帮助文�?
## fsys 成员列表

### fsys.lnk()

创建快捷方式

[返回对象:lnkfileObject](#lnkfileObject)

## fsys.lnk 成员列表

### fsys.lnk.enum

```aardio aardio
fsys.lnk.enum(
    function(dir,filename,fullpath,target,arguments){
        /*return false 停止遍历*/
    },0/*_CSIDL_DESKTOP*/
);

```

### fsys.lnk.getMsiTarget(lnk文件路径)

获取MSI创建�?Advertised 快捷方式指向的实际目标路�?
### fsys.lnk.getTarget(lnk文件路径)

获取快捷方式指向的目标路�?

支持Advertised Shortcut

### fsys.lnk.search

查找文件或快捷方式�?
成功返回启动路径与参�?
### fsys.lnk.search("目标文件名或参数","快捷方式标题")

全部参数可�?至少输入一个参�?
参数@1也可以是指定多个文件名的数组,

搜索快捷方式的文件名与标题支持模式匹配或忽略大小写的文本比，

直接搜索文件则必须精确匹配文件名�?
按下列顺序搜索文�?

如果未指定标题则先调�?fsys.searchFile �?EXE 目录及系统目录搜索，

接着搜索桌面快捷方式、应用程序快捷方�?
### fsys.lnk.searchInDesktop

在桌面查找文件或快捷方式�?
成功返回启动路径与参�?
### fsys.lnk.searchInDesktop("目标文件名或参数","快捷方式标题")

全部参数可�?至少输入一个参�?
参数@1也可以是指定多个文件名的数组�?
搜索快捷方式的文件名与标题支持模式匹配或忽略大小写的文本比较�?
直接搜索文件则必须精确匹配文件名

### fsys.lnk.searchLnk("文件名或参数","快捷方式标题", 0 /\*\_CSIDL\_DESKTOP\*/)

在桌面搜索快捷方式并返回路径

参数@3可省略�?
成功返回启动路径与参�?
### fsys.lnk.searchLnk("文件名或参数","快捷方式标题", 2 /\*\_CSIDL\_PROGRAMS\*/)

在开始菜单应用程序目录搜索快捷方式�?
成功返回启动路径与参�?
## lnkfileObject 成员列表

### lnkfileObject.arguments

参数

### lnkfileObject.description

附加说明

### lnkfileObject.filename

快捷方式默认文件�?可省略后缀�?

未指定则取版本信息中的产品名或目标文件名

### lnkfileObject.filepath

快捷方式加载或保存成功的文件路径

### lnkfileObject.free()

释放对象,

释放对象以后不能再使用此对象

### lnkfileObject.getIcon()

返回图标文件路径,以及图标索引

### lnkfileObject.hotkey

热键

### lnkfileObject.load()

[返回对象:lnkfileObject](#lnkfileObject)

### lnkfileObject.load(lnk文件路径)

载入快捷方式,返回fsys.lnk对象自身

### lnkfileObject.path

目标路径,设置该属性时:

如果workDir为空则设workDir为目标路径所在目�?
如果description为空则设为版本信息中的文件描�?
### lnkfileObject.pinToDesktop(false)

自桌面移除快捷方�?
### lnkfileObject.pinToDesktop(true)

添加快捷方式到桌�?
,参数@2如果为true则添加到所有用户程序组

### lnkfileObject.pinToPrograms(false,"子目录路�?)

自开始菜单程序组移除

可选指定多个子目录参数

如果指定了子目录则直接移除快捷方式所在父目录

### lnkfileObject.pinToPrograms(true,"子目录路�?)

添加到开始菜单程序组

可选指定子目录路径,参数@3如果为true则添加到所有用户程序组

### lnkfileObject.resolve(hwndParent,flags)

如果目标路径移动或丢�?

查找符合的目�?可能显示查找对话�?
### lnkfileObject.save(lnk文件存储路径)

保存快捷方式

如果指定了filename或path属�?参数也可以指定存储目�?
### lnkfileObject.setIcon(文件路径,图标索引)

设置图标文件路径

可以指定ico文件路径,也可指定EXE文件路径用于获取EXE图标

图标索引可省�?默认�?

### lnkfileObject.showCmd

显示参数

### lnkfileObject.workDir

工作目录

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/lnk.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/lnk.md')

