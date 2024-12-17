[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# util.table 库模块帮助文�?
## util.table 成员列表

### util.table.stringify

将表对象转换为源码格式�?
仅转换表包含的文本、数值、布尔值、嵌套表对象,

小数精度最大为 6 位、并自动清除小数尾部多余�?0,

如果表定义了 tostring 元方法、则转换为字符串

忽略其他类型,忽略循环引用的表

### util.table.stringify(表对�?格式化选项,默认排序�?

格式化选项�?true 仅第一级键值添加换�?

格式化选项指定缩进字符串时,则对所有下级键值添加换行与缩进

,默认排序表为可选参�?指定一个键名排序数�?
不在默认排序表中的名字按默认字典序排序输�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/util/table.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/util/table.md')

