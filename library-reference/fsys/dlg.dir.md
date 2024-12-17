[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.dlg.dir 库模块帮助文�?
## fsys.dlg 成员列表

### fsys.dlg.dir

打开新版目录对话�?

XP 系统自动降级�?fsys.dlg.openDir�?
需要导�?fsys.dlg.dir 库�?
### fsys.dlg.dir(path,hwndOwner,title,okLabel,clientGuid,multiSel)

打开目录对话框，所有参数可省略�?
参数@path 指定打开的目�?

参数@hwndOwner 指定父窗�?

参数@title 指定窗口标题

参数@okLabel 指定确定按钮上的文本,

参数 @clientGuid 指定单独存储对话框状态的 GUID�?
GUID 可以�?win.guid.valid 函数支持的参数类型（例如字符串格式） �?
参数@multiSel 如果�?true，则允许选择多目录并返回数组,

默认仅能选择单个目录并返回选中的路�?

取消返回 null

### fsys.dlg.dirs

打开新版目录对话�?允许多选�?
不支�?XP 系统�?
需要导�?fsys.dlg.dir 库�?
### fsys.dlg.dirs(path,hwndOwner,title,okLabel,clientGuid)

打开新版目录对话框，允许多选�?
所有参数可省略�?
参数@path 指定打开的目�?

参数@hwndOwner 指定父窗�?

参数@title 指定窗口标题

参数@okLabel 指定确定按钮上的文本,

参数 @clientGuid 指定单独存储对话框状态的 GUID�?
GUID 可以�?win.guid.valid 函数支持的参数类型（例如字符串格式）�?
参数@multiSel 如果为true，则允许选择多目录并返回数组,

默认仅能选择单个目录并返回选中的路�?

取消返回 null

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/dlg.dir.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/dlg.dir.md')

