[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.dlg.font 库模块帮助文�?
## win.dlg 成员列表

### win.dlg.font

通用字体对话�?
### win.dlg.font()

[返回对象:winDlgFontObject](#winDlgFontObject)

### win.dlg.font(winform父窗�?

创建通用字体对话�?
## winDlgFontObject 成员列表

### winDlgFontObject.chooseFont()

弹出选择字体对话�?成功返回::LOGFONT结构体的字体

[返回对象:logfontObject](#logfontObject)

### winDlgFontObject.logFont

用于初始化默认字体并返回选择后的字体,

选择字体以前可指定为LOGFONT对象，也可指定部分LOGFONT对象的字段，

选择字体时转换为buffer对象，选择字体成功转换回LOGFONT对象

[返回对象:logfontObject](#logfontObject)

### winDlgFontObject.pointSize

选择的字体大小，以十分之一点为单位

注意英文系统字体对话框会舍入为整点单位的十分之一

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/dlg/font.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/dlg/font.md')

