[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.log 库模块帮助文�?
## fsys 成员列表

### fsys.log("日志文件路径")

创建日志文件

### fsys.log()

[返回对象:fsyslogObject](#fsyslogObject)

## fsys.log 成员列表

日志文件

用于代替控制台在文件中输出变量或文本

### fsys.log.dump(变量)

显示变量的�?支持多参�?
注意仅显示普通table,string,number等类型的�?不显示函数等

### fsys.log.dumpJson(变量)

将对像转换为格式化的JSON文本并输出到控制�?
### fsys.log.print()

输出一行文�?支持多参�?
### fsys.log.printf("%s", )

输出格式化字符串,

格式化语法与string.format相同

### fsys.log.setPath("/config/app$.log")

设志日志文件路径,进程内全局有效,

如果不指定路�?默认设置�?/config/app$.log

## fsyslogObject 成员列表

### fsyslogObject.close()

关闭对象

### fsyslogObject.dump(变量)

显示变量的�?支持多参�?
注意仅显示普通table,string,number等类型的�?不显示函数等

### fsyslogObject.dumpJson(变量)

将对像转换为格式化的JSON文本并输出到控制�?
支持多参�?
### fsyslogObject.print()

输出一行文�?支持多参�?
### fsyslogObject.printf("%s", )

输出格式化字符串,

格式化语法与string.format相同

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/log.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/log.md')

