[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# 包含操作�?
运算符说明`$`包含操作�?
包含操作�?`$` 可以将外部文件在编译期嵌入到代码中以创建一个字符串对象�?
示例�?
```aardio aardio
import console;
console.log ( $"/my.txt" ) //my.txt 文件内容

```

在程序发布后，程序即可脱离源文件运行, 因为该文件已经被编译为一个普通字符串对象并内嵌到程序中了�?
如果 `$` 包含的文件路径以 `~/` �?`~\` 开始，并且查找文件失败�?aardio 会移除路径前面的 `~`，转换为单个 `\` �?`/` 开头的应用程序根目录路径继续查找�?
> 应用程序根目录在开发时指工程根目录（工程之外独立运行的 aardio 文件则指启动 aardio 文件所在目录），在发布后则指启�?EXE 所在目录�?
反之，如果包含的文件以单�?`\` �?`/` 开始，并且查找包含文件失败，aardio 不会在路径前面添�?`~` 到EXE目录下查找（EXE目录在开发时�?aardio 开发环境所在目录）�?
默认如果找不到包含文件会报错，但是如果被包含的文件路径前面添加一个问�? 找不到文件时则不会报错而是返回 null，示例：

```aardio aardio
import console;
console.log ( $"?不存在的路径" ) //不报错而是返回 null

```

需要注意的�?

1. 包含操作符在编译时生效�?   工程中内嵌资源目录包含的 aardio 代码文件在发布为 EXE 时会自动编译，但如果使用 string.loadcode 等函数将普通字符串作为 aardio 代码动态加载则不会在发布时编译该字符串。例如编�?aardio 代码 `string.loadcode("$'/example.txt'")` 时并不会编译 `"$'/example.txt'"` , 在发布时 `"$'/example.txt'"` 只是一个普通字符串�?2. 包含操作符嵌入的是原始二进制文件，不会对被包含的文件数据进行任何改变�?   即使你包含的�?aardio 源码文件，aardio 不会编译该文件。所以一般不应该�?`$` 操作符用于包�?aardio 源码文件。相反，如果通过内嵌资源目录包含 aardio 源码文件，发�?EXE 时则会自动自动编译该文件�?3. 被包含的文件程序发布后已内嵌到生成的 EXE 文件�?因此没有必要再将被包含的文件放入内嵌资源目录�?这样会导致同一个文件被包含两次 ）�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/language-reference/operator/include.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/language-reference/operator/include.md')
