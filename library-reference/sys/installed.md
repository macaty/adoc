[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sys.installed 库模块帮助文�?
## sys.installed 成员列表

用于检测指定的程序是否安装

如果需要获取更多信�?请参考源码自注册表读�?

MSI 安装程序可用 COM 对象 WindowsInstaller.Installer 读取更多信息

### sys.installed.find()

检测是否已安装指定的程�?

参数指定要在显示名称中搜索的字符�?支持模式匹配

成功返回包含 DisplayName、Version、DisplayVersion 字段的表,

如果存在指示安装目标位置的字�?InstallLocation 则包含该字段,

可能包含 InstallDate 字段用于指示安装日期,这是8个字符表示的日期,

极个别的安装程序缺少 InstallDate 字段,

未安装该程序则返�?null

### sys.installed.programs()

返回所有已安装的程�?

返回值为�?键为已安装程序的ID,

值为安装信息,包含 DisplayName �?Version 字段,

DisplayName 为显示名�?Version 字段的版本数值可作为 fsys.version 的参数解析为版本�?
另安装信息包�?个可选字段：DisplayVersion,InstallDate

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/sys/installed.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/sys/installed.md')

