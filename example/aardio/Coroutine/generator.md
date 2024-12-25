[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 纤程生成�?
```aardio aardio
//纤程生成�?import console;

function fib(max){
    var a, b = 1, 1;
    while a < max {
        fiber.yield( a );
        a, b = b, a+b;
    }
}

/*
纤程与迭代器都是交换代码控制权、分离代码逻辑的方�?
而纤程生成器则是两者结合的应用,使用 fiber.generator 将函数自动转换为纤程,
并使用该纤程自动生成迭代器�?*/
for v in fiber.generator(fib,console.getNumber( "请输入斐波那契数列范�?" )) {
    console.log( v )
}

console.pause()

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/aardio/Coroutine/generator.md)

