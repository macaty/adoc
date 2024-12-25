[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 字符串生成器

```aardio aardio
//字符串生成器
import console;
import string.builder;

//创建字符串生成器（内部基于动态指针）
var bs = string.builder() //可右键点 string.builder，然后点「跳转到定义�?
//设置初始�?bs.assign("  初始�?)

for(i=1;100;1){
    bs.append( tostring(i) );//追加字符�?    bs.appendf( "%d",i );
}

//清除两侧空格
bs.trim()

//字符串操作函�?console.log("右侧�?个字�? ,bs.rightString(3) );

//转换为字符串
console.log("转换为字符串" ,tostring(bs) );

console.log("预分配内存大�?,bs.capacity())

console.log("实际存储内容大小",bs.size())

//重新调整字符串长�?bs.resize(10)

//释放多余的内�?bs.reserve(0);

//bs对象在不使用时可自动释放，但也可以主动调用free()函数尽量释放不用的内�?bs.free(); //在重新分配内存之前就不能再读写该内存�?
if( ! bs.capacity() ){
    //但是重新分配内存又可以用�?    bs.reserve(100);
}

bs += "重新分配内存又可以用�?;

console.log(bs)

console.log( bs.str() )

//可如下与结构体连�?bs += {BYTE x[] ='dbcd\0'}
console.log( bs.toUtf16() )

console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/aardio/Raw/string.builder.md)

