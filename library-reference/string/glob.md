[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# string.glob 库模块帮助文�?
## string 成员列表

### string.glob

glob 模式匹配工具�?
glob 模式用于匹配文件名或文件路径，主要通配符包�?

- `*` 匹配任意个字�?不含路径分隔�?

- `**` 匹配任意层级的目�?含路径分隔符)

- `?` 匹配单个字符

  `[abc]` 匹配方括号中的任意单个字�?
- `[!abc]` �?`[^abc]` 匹配不在方括号中的任意单个字符�?

注意�?`\` 不用于转义，模式中的 `/` 自动转换�?`\` 进行匹配�?
创建 glob 模式匹配工具

### string.glob()

[返回对象:stringGlobObject](#stringGlobObject)

### string.glob(pattern)

glob 模式匹配工具�?
参数 @pattern 可指定符�?glob 语法的模式文本，或包含模式文本的数组�?
可省略参数�?
## stringGlobObject 成员列表

### stringGlobObject.clear()

清空所�?glob 模式�?
### stringGlobObject.load(模式文件)

自文件加载并添加 glob 模式，不清空之前的模式�?
每行文本指定一个模�?#字符开头的为注�?

忽略首尾空格，忽略空�?
### stringGlobObject.push(模式)

添加 glob 模式�?
参数 @1 可以是符�?glob 语法的模式文本，或包含模式文本的数组

### stringGlobObject.test()

测试一个字符串是否匹配

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/string/glob.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/string/glob.md')

