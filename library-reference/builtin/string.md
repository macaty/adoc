[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# builtin.string 库模块帮助文�?
## string 成员列表

### string.cmpMatch( ,"字符串参�? )

使用完全匹配比较字符串，忽略大小写，相同返回 true�?
否则使用模式匹配搜索子串，忽略大小写，找到返�?true�?
改用 string.indexOf 函数可禁用模式匹配查找子串�?
### string.concatUtf16(str,...)

将所有参数转换为 UTF-16 字符串并连接后返回�?
参数可以是数值，字符串，UTF-16 编码字符串�?
忽略 null 值参�?
### string.crlf(字符�?回车换行,合并空行�?

自动调用 tostring 函数转换传入参数 @1 为字符串�?
此函数格式化参数 @1 的回车换行或单独的回车换行符为参�?@2 指定的换行标记�?
参数 @2 默认�?'\\r

'，如果改为为 '

' 则格式化为单个换行符�?
可选用参数 @3 指定合并空行后保留的空行数，省略则不合并�?
注意字符串字面值解析换行的规则:

双引号或反引号内字符串只有换行没有回�?

单引号内字符串解析时忽略所有回车换�?

使用/\*块注释\*/包含字符串则总是将换行规范解析为回车换行组合

### string.each

创建适用�?for in 语句的迭代器,

用于分行匹配字符�?

可将返回迭代器传�?table.array 生成数组

### string.each(字符�?模式�?行分隔符)

必须使用参数@2指定模式�?

查找模式串中可用圆括号创建捕获分组自定义迭代器返回值个�?

行分隔符支持模式匹配语法,可省�?
### string.expand

重复替换直到找不到匹�?

可用于展开字符串中的环境变�?
### string.expand(字符�?查找模式�?替换函数)

在字符串中重复执行替换操�?

直到参数@2指定的模式串找不到匹�?

省略参数@2,@3则默认展开百分号包含的进程环境变量

可用于展开文件路径中的环境变量

注意即使替换函数返回null,此函数仍然会替换为空�?

如果替换结果为空字符�?此函数返�?null

### string.fromCharCode()

使用1个或多个 Unicode 编码值转换为 UTF-8 字符�?
参数可以指定1个或多个Unicode编码数�?可指定大�?x10000的编�?

不可直接传入数组作为参数

### string.getenv("变量�?)

读取当前进程环境变量

成功返回字符�?失败返回 null

### string.gfind(字符�?模式�?开始位�?

```aardio aardio
for i,j,group1  in string.gfind( /*查找字符�?/,"(.)") {

}

```

### string.isUtf8()

快速检测字符串是否包含UTF8编码

空字符串返回null

### string.lines

创建用于for in 语句的迭代器按行拆分字符串�?
可用模式串自定义行分隔符，此函数�?string.splitEx 函数使用相同的拆分规则�?
可将返回迭代器传�?table.array 生成数组�?
按行读取文件请使�?io.lines 函数�?
### string.lines(字符�?行分隔符,列分隔符,最大列�?

按行拆分参数 @1 传入的字符串，传�?null 或空串字符串忽略不操作�?
可选用参数 @2 自定义行分隔符，支持模式匹配语法�?
可选用参数 @3 自定义列分隔符，支持模式匹配语法�?
所有分隔符模式串可用括号创建捕获组，首个捕获组如下处理�?
- 模式串尾部有 $ 符号，则捕获组放到上个拆分结果尾部�?
- 模式串头部有 ^ 符号，则捕获组放到下个拆分结果头部�?
- 模式串头部有^ 符号尾部�?$ 号则捕获组本身拆分为一个单位�?

  如果返回行分隔符，则迭代器的�?2 个循环变量为 true�?

可选用参数 @4 限定最大拆分列数目�?
如果不指定列分隔符则循环返回字符串，否则返回列数组�?
### string.loadcode

加载并执�?aardio 代码或文�?返回 HTML 模板输出�?HTML 代码

如果当前应用未定�?response 对象,请使�?print 函数替代�?
此函数也可以用于�?HTML 格式的任意字符串模板�?
但非 HTML 格式的字符串开始部分必须是 aardio 模板标记

### string.loadcode("代码文件",...)

加载并执�?aardio 代码或文�?

返回 HTML 模板输出�?HTML 代码,失败返回空�?错误信息�?
参数@1,�?loadcode 函数相同,其他参数作为模板参数传给被调用的文件,

在被调用文件的函数外部可使用 owner 参数获取首个模板参数,

也可以使�?..获取多个模板参数

### string.map

搜索并返回搜索结果数�?

并调用映射函数转换数组中的每个匹配结果为新的�?

注意如果模式串中使用括号指定了多个分�?

映射函数会有多个对应的回调参�?
### string.map(字符�?模式,映射函数)

参数@1指定要查找的字符�?

参数@2可以指定模式�?或包含多个表达式的数�?

省略则默认为 `[-\d]+`,并且参数@3的默认值会被更换为tonumber

可选用参数@3指定映射函数,

返回值为匹配的字符串数组,如果有多个捕获分组则返回二维数组

如果参数@2不是数组而是�?则返回相同结构的�?

每个键对应的值更新为参数表中同名键指定的模式串的匹配结果�?
### string.matches("字符�?,"模式�?)

全局匹配并将匹配结果返回为数�?
每次匹配成功的多个返回值存为成员数�?
即使没有匹配到任何结�?也会返回一个空数组

### string.reduce

使用string.match依次匹配多个模式�?逐步缩减并返回最终匹配结�?
### string.reduce(字符�?模式,...)

参数@1指定要查找的字符�?

参数@2开始指定一个或多个模式�?

使用前面一个的匹配结果作为后面一次匹配的条件,

逐步缩减并返回最终匹配结�?

也可以在参数@2中使用一个数组指定多个模式串

### string.removeBom(字符�?

如果字符串开始为UTF8 BOM，则返回移除�?BOM 的字符串�?
如果字符串开始为 UTF-16 BOM,则移�?BOM 并返回转换为 UTF-8 编码的字符串,

否则直接返回参数

### string.replaceUnmatched

在一个或多个与指定模式不匹配的部分进行替�?
### string.replaceUnmatched(源字符串,替换模式�?替换对象,排除模式�?,排除模式�?...)

在源字符串中保留与一个或多个排除模式串匹配的部分�?
然后对剩余的部分进行单独替换�?
"替换模式�?,"替换对象"等参数与 string.replace 函数要求一致，

"替换对象"可以是新的字符串、替换表或替换函数�?
可以指定一个或任意多个"排除模式�?�?
函数返回替换后的字符串与替换次数�?
### string.repline

按行替换字符�?返回替换后的字符�?

此函数仅返回替换后的新字符串,只有一个返回�?
### string.repline(源字符串,模式�?替换�?替换次数)

模式串用于匹配所有的单行文本,

替换串与 string.replace 用法相同

替换次数指的也是每一行内部进行替换的最大次�?不指定则不限�?
### string.repline(源字符串,模式�?替换函数,替换次数)

模式串用于匹配所有的单行文本,

替换函数�?string.replace 用法相同

,

替换次数指的也是每一行内部进行替换的最大次�?不指定则不限�?
### string.repline(源字符串,模式�?替换�?替换次数)

模式串用于匹配所有的单行文本,

替换表与 string.replace 用法相同

,

替换次数指的也是每一行内部进行替换的最大次�?不指定则不限�?
### string.search(回调函数,字符�?模式�?...)

模式匹配搜索.

可以指定1个或多个模式�?

此函数使用前面表达式的结果作为后面表达式的查询字符串,

每一个模式串都支持全局搜索并可以返回多个匹配结�?

最后一个表达式的匹配结果作为参数回调参数@1指定的函�?

每一个模式串参数都可以使用函数或 lambda表达式替�?

用于作为筛选器筛选上次的匹配结果,筛选器可以返回新的字符�?

返回非字符串类型则用于指定是否保留上次的匹配结果,

如果参数@1是一个数�?则将匹配结果添加到该数组,如果有多个捕获分组则返回二维数组,

如果参数@1是数组则返回该数�?否则函数无返回�?
### string.setenv("变量�?,"变量�?)

设置当前进程环境变量

参数@2�?null 或省略则删除参数@1指定的环境变�?
### string.splitEx

使用模式匹配语法拆分字符串，返回拆分后的字符串数组�?
此函数与 string.lines 迭代器使用相同的拆分规则�?
### string.splitEx(字符�?分隔符模式串,最大拆分次�?开始位�?

使用模式匹配语法拆分字符串，返回拆分后的字符串数组�?
参数 @1 传入 null 值或空字符串返回空数组�?
分隔符模式串可用括号创建捕获组，首个捕获组如下处理：

- 模式串尾部有 $ 符号，则捕获组放到上个拆分结果尾部�?
- 模式串头部有 ^ 符号，则捕获组放到下个拆分结果头部�?
- 模式串头部有^ 符号尾部�?$ 号则捕获组本身添加到返回数组中�?

省略分隔符模式则按行拆分�?
兼容回车、换行、回车换行等不同换行风格，空行不合并�?
最大拆分次数可省略（不限次数），分隔符单独加入拆分结果时拆分次数会对齐为奇数�?
开始位置以字节为单位，省略则默认从开始拆分�?
### string.table

解析以行为单位的字符串属性表�?
类似功能�?string.list 支持用引号包含跨行的字段值，

�?string.table 仅将引号作为字面值处理�?
### string.table(字符�?键值分隔模�?行分隔模�?行首注释�?

解析以行为单位的字符串属性表�?
除参数@1 以外其他所有参数都可以省略�?
键值分隔模式默认为 "\\s\*\[:=\]\\s\*"，也就是忽略前后空白的冒号或等号�?
行分隔符默认兼容回车换行、换行、单回车等行分隔符�?
默认不指定行首注释符，该参数仅支持字节码，例�?'#'#�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/builtin/string.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/builtin/string.md')
