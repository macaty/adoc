[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# golang.string 库模块帮助文�?
必读，点这里展开

golang.string() 创建 Go 字符串�?�?Go 函数中可作为 \*string 类型指针参数使用�?Go 函数中用 \* 号解引用访问 aardio 字符串�?
�?Go 中可修改字符串�?�?aardio 中使�?tostring 转换 golang.string 对象为字符串�?或者访�?golang.string 对象�?value 属�?都可以获取到 Go 修改后的值�?
应在调用 Go 函数后立即访�?value 属性，或调�?tostring 转换字符串�?aardio 会立即重新分配安全的内存存储新的值，Go 随后会安全回收分配的内存（不会泄漏）�?而且只有�?Go 修改内存�?aardio 才会转换，不修改不会浪费内存，也不会有多余的转换�?
如果 golang.string 的构造参数是非字符串、非 buffer、非 null 参数�?aardio 会先将其转换�?JSON，再转为 Go 字符串�?
如果�?JSON 存储了这样的 Go 字符串，
�?Go 修改字符串时必须同样写入 JSON�?aardio 在读取新的字符串值时，也同样会用 JSON 自动解析为对象�?使用 golang.string �?value 属性可以读取解析后的对象值�?
任何时候都可以通过 value 属性重新设�?golang.string 存储的值�?
请参考：aardio 范例 / 调用其他语言 / Go 语言

## golang 成员列表

### golang.string()

创建 Go 字符串�?
参数@1可指�?buffer、string、null 类型的值�?
如果指定其他类型值自动转换为 JSON 字符串�?
Go 修改字符串后 aardio 也会自动解析为对象�?
使用 golang.string 对象�?value 属性可以读写存储值�?
Go 函数的参数类型必须声明为 \*string 指针�?
�?Go 调用返回以后，建议立即用 tostring 转换�?aardio 字符串�?
因为 Go 的内存回收器稍后会回�?Go 字符串的内存（至少在调用结束那一刻并不会立即回收）�?
转换以后此对象的内部指针即安全地指向 aardio 分配的内存�?
只要正确使用，go.string 不会造成内存泄漏�?
如果不需要在 Go 中修改字符串�?
更简单的方法是直接传 2 个参数（aardio 字符串，字符串长度）

代替 Go 字符串�?这种方式是传值，不是传指�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/golang/string.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/golang/string.md')

