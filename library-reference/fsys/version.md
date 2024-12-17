[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.version 库模块帮助文�?
转换字符串规�?
fsys.version 对象可作为参数传�?tostring 函数转换为字符串格式�?tostring 函数的第 2 个参数可选指定格式化串（ 语法�?string.format 函数相同）�?如果不指定格式化串，默认格式化串�?"%d.%d.%d.%d"�?如果 revision �?0 ，默认格式化串为 "%d.%d.%d"�?如果同时 build 也为 0，默认格式化串为 "%d.%d"�?
## fsys 成员列表

### fsys.version("0.0.0.0")

创建版本�?支持大于小于相等比较,可转换为字符串或数�?

参数可以为空,或者数�?字符�?表对象等

如果参数为字符串,忽略无关文本,版本号后的文本提取为releaseType

文本中提取的版本号为2~4组以圆点、或其他标点、空格分隔的数�?
### fsys.version()

[返回对象:fsysVersionObject](#fsysVersionObject)

## fsys.version 成员列表

用于创建与解析版本号�?
fsys.version 对象可作为参数传�?tostring 函数转换为字符串格式�?
tostring 函数的第 2 个参数可选指定格式化串（ 语法�?string.format 函数相同）�?
如果不指定格式化串，默认格式化串�?"%d.%d.%d.%d"�?
如果 revision �?0 ，默认格式化串为 "%d.%d.%d"�?
如果同时 build 也为 0，默认格式化串为 "%d.%d"

### fsys.version.getInfo()

[返回对象:fsysVersionInfoObject](#fsysVersionInfoObject)

### fsys.version.getInfo(执行文件路径)

返回版本信息

## fsysVersionInfoObject 成员列表

### fsysVersionInfoObject.codePage

代码�?
### fsysVersionInfoObject.companyName

公司�?
### fsysVersionInfoObject.companyNameUnicode

公司�?Unicode编码

### fsysVersionInfoObject.fileDescription

文件描述

### fsysVersionInfoObject.fileDescriptionUnicode

文件描述,Unicode编码

### fsysVersionInfoObject.fileVersion

[返回对象:fsysVersionObject](#fsysVersionObject)

### fsysVersionInfoObject.internalName

内部�?
### fsysVersionInfoObject.internalNameUnicode

内部�?Unicode编码

### fsysVersionInfoObject.language

语言代码

### fsysVersionInfoObject.originalFileName

原始文件�?
### fsysVersionInfoObject.originalFileNameUnicode

原始文件�?Unicode编码

### fsysVersionInfoObject.productName

产品名称

### fsysVersionInfoObject.productNameUnicode

产品名称,Unicode编码

### fsysVersionInfoObject.productVersion

[返回对象:fsysVersionObject](#fsysVersionObject)

## fsysVersionObject 成员列表

### fsysVersionObject.build

发行版本号中用于表示编译版本或补丁版�?16位数�?
该版本号表示兼容的问题修�?
### fsysVersionObject.major

发行版本号中的主版本�?8位数�?
表示较大或不兼容的改�?
### fsysVersionObject.minor

发行版本号中的副版本�?8位数�?
表示向下兼容的改动或新增功能

### fsysVersionObject.releaseType

发行版本类型,例如:"alpha", "beta","RC" �?
可选字�?字符串类�?
### fsysVersionObject.revision

内部修订版本�?
注意版本号转换为一个数值时忽略此版本号

### fsysVersionObject.valid()

版本号是否有�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/version.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/version.md')

