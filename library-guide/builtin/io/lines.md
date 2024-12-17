[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# 分行迭代读取文件

io.lines(pathOrFile = io.stdin )

io.lines 自动打开通过 @pathOrFile 参数指定路径的文件�?
@pathOrFile 参数也可以是使用 io.file 打开的文件对象，省略 @pathOrFile 参数则使用默认�?io.stdin �?
如果指定文件路径，io.lines 使用文本模式打开文件，文本模�?`'\0'`, `'\x1A'` 为终止符。如果需要读�?`'\x1A'` 或�?`'\0'`，请调用 `io.files(path,"rb")` 以二进制模式打开文件对象，然后就文件对象指定�?io.lines 的第一个参�?@pathOrFile�?
io.lines 创建一�?[迭代器](../../../language-reference/statements/looping.html#for-in)�?支持�?[泛型for](../../../language-reference/statements/looping.html#for-in) 循环中逐行读取文件，在读取完毕以后自动关闭文件对象。使�?io.lines 可以避免一次性读取太大的文件�?
```aardio aardio
import console;

for line in io.lines("d:\test.txt") { //io.lines()返回的迭代器函数每次读取文件中的一�?    console.log(line);
}

```

使用 file.read 函数可以实现类似的功能：

```aardio aardio
import console;

var file = io.file("d:\test.txt")

while( var line = file.read() ) {
    console.log(line);
}

file.close();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-guide/builtin/io/lines.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-guide/builtin/io/lines.md')

