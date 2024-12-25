[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.codepage 库模块帮助文�?
## fsys.codepage 成员列表

### fsys.codepage.load("文件路径",源编�?目标编码)

读取文件,参数2,3都是可选参�?

可自动识别文件编�?并自动转换为目标编码,

目标编码默认�?5001

### fsys.codepage.load(文件路径,"unicode")

读取UNICODE（小尾序）编码文�?
并自动转换为UTF8编码,

返回文件内容,以及读取内码

### fsys.codepage.load(文件路径,"unicodeFFFE")

读取UNICODE（大尾序）编码文�?
并自动转换为UTF8编码,返回文件内容,以及读取内码,

注意 unicodeFFFE �?BOM �?'\\xFE\\xFF',反过来的�?
### fsys.codepage.load(文件路径,"utf-8")

读取UTF-8编码文件

并自动转换为UTF8编码,

返回文件内容,读取内码

### fsys.codepage.save(文件路径,str,"unicode")

将参数@2指定的字符串存为UNICODE（小尾序）编码文�?并添加BOM编码标识

可选以参数@4指定输入代码�?默认�?5001�?
如果参数 @5 �?true 则禁�?BOM 头，默认�?false�?
### fsys.codepage.save(文件路径,str,"unicodeFFFE")

将参数@2指定的字符串存为UNICODE（大尾序）编码文�?并添加BOM编码标识,

注意 unicodeFFFE �?BOM �?'\\xFE\\xFF',反过来的�?
可选以参数@4指定输入代码�?默认�?5001�?
如果参数 @5 �?true 则禁�?BOM 头，默认�?false�?
### fsys.codepage.save(文件路径,str,"utf-8")

将参数@2指定的字符串存为UTF-8编码文件,并添加BOM编码标识

可选以参数@4指定输入代码�?默认�?5001�?
如果参数 @5 �?true 则禁�?BOM 头，默认�?false�?
### fsys.codepage.save(文件路径,str,"utf-8-nobom")

将参数@2指定的字符串存为UTF-8编码文件,不添加BOM编码标识

可选以参数@4指定输入代码�?默认�?5001�?
如果参数 @5 �?true 则禁�?BOM 头，默认�?false�?
### fsys.codepage.save(文件路径,str,0)

将参数@2指定的字符串以ANSI编码存为文件,参数@3指定输出代码�?
可选以参数@4指定输入代码�?默认�?5001

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/codepage.md)

