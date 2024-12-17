[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# julia.value 库模块帮助文�?
## julia.value 成员列表

### julia.value.build()

将参数传入的 aardio 对象转换�?Julia 对象,

传入指针类型时，不作任何转换

### julia.value.importType("字符串参�?)

导入并返�?Julia 类型对象指针，例�?importType("any\_type")

### julia.value.parse()

将参数传入的 Julia 对象原始指针转换�?aardio 对象,

参数传入指针时必须是 Julia 对象原始指针,非指针类型参数直接返�?

无法转换的对象直接返回原指针

### julia.value.topointer()

取出 Julia 对象指针指向的指针�?

返回的已经是普通内存指针，不能再作�?Julia 对象指针使用

### julia.value.typeof()

返回 Julia 对象指针的数据类�?返回值为字符�?

如果传入参数不是指针，返�?null

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/julia/value.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/julia/value.md')

