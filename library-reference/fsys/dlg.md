[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.dlg 库模块帮助文�?
## fsys.dlg 成员列表

系统文件对话框�?
请注意：文件对话框会改变当前目录，导致相对路径（例如 "./res/"）位置变化�?
路径首字符用单个斜杠或反斜杆表示「应用程序根目录」的写法更可靠，

例如：（例如 "/res/"）�?
可以使用 fsys.setCurDir 函数设置当前目录�?
很多组件（例如文件对话框）都可能会悄悄改变当前目录�?
而「应用程序根目录」则是固定不变的

### fsys.dlg.OPENFILENAME()

[返回对象:OPENFILENAMEObject](#OPENFILENAMEObject)

### fsys.dlg.OPENFILENAME(缓冲区大�?默认文件�?

创建 OPENFILENAME 结构�?
### fsys.dlg.open

打开选择单文件对话框

### fsys.dlg.open(指定文件类型,对话框标�?默认目录,父窗�?选项参数,默认文件�?

打开选择单文件对话框，所有参可选�?
文件类型以竖线分�?并以坚线分隔类型说明与后缀�?例如

"所有文件\|\*.\*\|文本文件\|\*.txt;\*.md\|"

一个类型说明匹配多个后缀名应以分号分�?
### fsys.dlg.openDir

打开选择目录对话框，

建议改用 fsys.dlg.dir

### fsys.dlg.openDir()

打开选择目录对话框�?
### fsys.dlg.openDir(目录,父窗�?标题,窗口标题)

打开选择目录对话�?

所有参数都是可选参数�?
### fsys.dlg.openEx

打开选择多文件对话框

### fsys.dlg.openEx(指定文件类型,对话框标�?默认目录,父窗�?选项参数,缓冲区大�?

打开选择多文件对话框，所有参数可选�?
文件类型以竖线分�?并以坚线分隔类型说明与后缀�?例如

"所有文件\|\*.\*\|文本文件\|\*.txt;\*.md\|"

一个类型说明匹配多个后缀名应以分号分隔，

第一个返回值为一个数�?包含一个或多个被选定的文件路�?
多选则会返回第二个数组�?包含被选目录路径以及多个文件名

### fsys.dlg.save

显示保存文件对话框框

覆盖已存在的文件时不显示确认对话框�?
### fsys.dlg.save(指定文件类型,对话框标�?默认目录,父窗�?选项参数,默认文件�?

显示保存文件对话框框,所有参数为可选参�?
文件类型以竖线分�?并以坚线分隔类型说明与后缀�?例如

"所有文件\|\*.\*\|文本文件\|\*.txt;\*.md\|"

一个类型说明匹配多个后缀名应以分号分�?
### fsys.dlg.saveOp

显示保存文件对话框框,

覆盖已存在的文件时显示确认对话框（overwrite prompt�?
### fsys.dlg.saveOp(指定文件类型,对话框标�?默认目录,父窗�?默认文件�?

显示保存文件对话框框,

覆盖已存在的文件时显示确认对话框�?
所有参数为可选参�?
文件类型以竖线分�?并以坚线分隔类型说明与后缀�?例如

"所有文件\|\*.\*\|文本文件\|\*.txt;\*.md\|"

一个类型说明匹配多个后缀名应以分号分�?
## OPENFILENAMEObject 成员列表

### OPENFILENAMEObject.defExt

默认后缀�?
### OPENFILENAMEObject.defaultFileName

默认文件�?
### OPENFILENAMEObject.filter

指定文件类型

例如'所有文件\|\*.\*\|文本文件\|\*.txt\|'u

### OPENFILENAMEObject.flags

一个或多个\_OFN\_前缀选项

参考MSDN文档

### OPENFILENAMEObject.hwndOwner

父窗口句�?
### OPENFILENAMEObject.initialDir

初始目录

### OPENFILENAMEObject.open()

打开文件对话�?返回文件�?
### OPENFILENAMEObject.save()

打开保存文件对话�?返回文件�?
### OPENFILENAMEObject.title

标题

### 自动完成常量

\_BIF\_BROWSEFORCOMPUTER=0x1000

\_BIF\_BROWSEFORPRINTER=0x2000

\_BIF\_BROWSEINCLUDEFILES=0x4000

\_BIF\_BROWSEINCLUDEURLS=0x80

\_BIF\_DONTGOBELOWDOMAIN=0x2

\_BIF\_EDITBOX=0x10

\_BIF\_RETURNFSANCESTORS=0x8

\_BIF\_RETURNONLYFSDIRS=0x1

\_BIF\_SHAREABLE=0x8000

\_BIF\_STATUSTEXT=0x4

\_BIF\_USENEWUI=0x50

\_BIF\_VALIDATE=0x20

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/dlg.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/dlg.md')

