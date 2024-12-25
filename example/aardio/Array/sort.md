[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 内置排序

```aardio aardio
//排序
import console.int;

//创建数组，可以用分号（或逗号）分隔数组成员�?var array = {2,46,5,17,1,2,3};

//table.sort() 函数用于排序数组�?table.sort(array);
console.dumpTable(array);

//自定义排�?table.sort(array,function(next){
    //可以�?> �?< 比较，但不能�?>= �?<= ，元素相等不能返�?true�?    return owner > next;
})
console.dumpTable(array);

/*
排序数组�?table.sort() 函数就可以了�?后面范例中收录的其他排序算法仅供参考�?*/

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/aardio/Array/sort.md)

