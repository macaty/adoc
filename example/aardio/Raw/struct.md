[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 结构�?
```aardio aardio
//结构�?import console;

/*
�?aardio 中结构体就是表对象，
但在每个成员名前指定了该成员的原生类型�?如下 x,y 成员的类型就�?int 类型�?2位有符号整数，大写表�?2位无符号整数）�?
相关文档�?https://www.aardio.com/zh-cn/doc/library-guide/builtin/raw/struct.html
*/
var pt = {
    int x;
    int y;
}
/*
注意：原生类型必须写在结构体或�?API 声明内部�?*/

//结构体传�?API 参数会自动转换为原生结构体指针（调用结束自动释放原生指针�?::User32.GetCursorPos(pt);
console.log(pt.x,pt.y);

/*
不声明直接调�?API 时，所有结构体参数都是输出参数�?所以下面这样写也是可以的：
*/
var ret,pt = ::User32.GetCursorPos({int x;int y;});

//结构体会自动初始化，所�?0, null, false 等值不必如下显式指定�?var ret,pt = ::User32.GetCursorPos({int x = 0;int y = 0;});

//我们可以�?class 声明结构体类�?class PT{
    int x;
    int y;
}

//用结构体类型创建结构�?var pt = PT();
::User32.GetCursorPos(pt);

//aardio 已经默认声明�?::POINT,::RECT 这些常用结构�?var pt = ::POINT();
::User32.GetCursorPos(pt);
console.log(pt.x,pt.y);

//结构体在调用 API 时转换为原生指针，调用结束释放原生指针�?//如果不想在调用结束自动释放结构体指针，就需要先将结构体复制到内存，如下�?var ptBuffer = raw.buffer({int x;int y;});
::User32.GetCursorPos(ptBuffer);//使用结构体指针作为参数调�?API
var pt = raw.convert(ptBuffer,{int x;int y;});//自内存中还原结构�?console.log(pt.x,pt.y);

console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/aardio/Raw/struct.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/aardio/Raw/struct.md')

