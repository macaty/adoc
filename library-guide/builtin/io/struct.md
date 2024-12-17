[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# 读写结构�?
file 对象支持读写结构�? struct )，请参�? [io 函数](file.html) [原生数据类型](../raw/datatype.html)

## 读写结构�?
[file.write](file.html#write) �?[file.read](file.html#read) 都可以指定任意多个参数，按顺序在文件流中写入或读取数据。而这两个函数都支持结构体( struct )�?
使用结构体可以非常方便地从文件中读写二进制数据�?
**示例代码�?*

```aardio aardio
import console;

//自定义一个结构体
var testStruct ={
    int a = 134;
    BYTE b[] ="我是配置文件";
}

//创建一个文件对�?var file = io.file("/bin.bin","w+");

//写入结构�?file.write('下面是一个结构体\r\n',testStruct); //可以写入任意多个参数
//从缓冲区写到文件
file.flush();

//移动读写指针到文件开�?file.seek("set");
//再读取结构体
var desc,testStruct = file.read("%s"/*%s表示读取一�?/,testStruct);

//关闭文件
file.close();

console.print( desc );
console.dumpTable( testStruct );
console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-guide/builtin/io/struct.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-guide/builtin/io/struct.md')

