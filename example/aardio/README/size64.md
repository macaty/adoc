[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 64 位长整数

```aardio aardio
//64 位长整数
/*
语法文档写了不看，这里再写一遍，再重复问就说不过去了�?我们做不到十全十美，完美从来就不是免费的，其成本有可能昂贵到我们无法仰望�?*/
import console.int;

/*
某些流行的编程语言甚至不支持无符号数，
没有多少人会认为这是个问题且有必要经常讨论�?
在很多编程语言里都只支�?double 数值�?没有多少人会认为这是个问题且有必要经常讨论�?
aardio 的有效整数上限是正负 (2**53 - 1)�?00 万年内应该够用了�?而且 aardio 额外专门提供�?64 位无符号数类�?math.size64 �?
如果这还不够，aardio 还提供了
支持大数运算�?math.bignum 以及 System.Numerics.BigInteger 库�?*/

//创建 64 位无符号整数
var num = math.size64("0xFFFFFFFFFFFFFFFF");
console.log(num);

//可以做常用运�?console.log(num - 1);

//可以用于静�?64 位无符号整型 LONG �?var struct = {
    LONG v = num;
}

/*
可以调用 format 函数方便地转换为容量字符串�?虽然无符号长整数的初衷通常是用来表示容量�?
但这里容量的有效上限�?7.99PB，这实际上是 double 的有效整数上限�?超过 8PB 会显�?-1 字节�?
另外这是操作系统接收 64 位无符号整数并返回的值，
这锅 aardio 不背�?*/
console.log(math.size64(9007199254740991).format() );

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/aardio/README/size64.md)

