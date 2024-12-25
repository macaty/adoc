[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 共享结构�?
```aardio aardio
//共享结构�?import console;
import julia;

//Julia 内定义一个结构体
julia.eval("
struct B
    Items::NTuple{3, Int32}
    function B()
        return new((1, 2, 3))
    end
end
");

//执行 Julia 代码，并返回结构体对象�?var structObj = julia.evalStruct("structObj = B()",{
    int items[3]; //参数 @2 必须指定 aardio 结构体（或结构体类）
});

/*
structObj 是一�?raw.struct 对象�?对该对象的读写操作都会与 Julia 内存同步�?当然这点性能影响微乎其微，一般可以不管�?
将字段值读出来再操作效率会更好�?或者用 structObj.get() structObj.set() 函数也可以�?*/
var items =  structObj.items;

//读数组�?console.log( items[3] );

/*
修改 aardio 结构体会同步修改 Julia 的结构体，两者共享内�?必须读写 structObj 的成员或调用 get,set 函数才会触发 raw.struct 的内存同步操作�?*/
structObj.items = {10,20,30}

//可以看到 Julia 结构体的值已经被改了
console.log( julia.eval("structObj.Items[3]") )

/*
Julia 虽然返回的是结构体指针，并且�?aardio 结构体兼容�?�?Julia 在结构体指针的前面藏了一个类型字段�?
所以我们无法将 aardio 创建的结构体直接传给 Julia�?但可以用 aardio 调用 Julia 执行代码并创建结构体�?*/

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Julia/Julia.Struct.md)

