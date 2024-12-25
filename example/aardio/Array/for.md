[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 循环遍历数组

```aardio aardio
//循环遍历数组
import console.int;

//创建纯数�?var array = {123,456,789}

//纯数组用 for in 语句遍历可保持数组索引顺序�?for(i,v in array){
    console.log(i,v);
}

//如果表包含了非数组成�?array.name = "数组";

/*
这时候应当改用计数循环遍历数组成�?*/
for(i=1;#array;1){
    var v = array[i];
    console.log(i,v);
}
console.more(1,true);

var array = {
    [0] = 123;
    [1] = 456;
    [2] = 789;

    //下面定义元表
    @{
        length = 5;
        _startIndex = 0;
    }
}

/*
table.eachIndex() 创建的迭代器也可以顺序遍历表的数组成员�?并且支持�?length 属性或 length 元属性自定义数组大小�?支持�?_startIndex 元属性自定义数组起始索引�?*/
for i,v in table.eachIndex(array){
    console.log(i,v);
}

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/aardio/Array/for.md)

