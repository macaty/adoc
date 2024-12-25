[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# 取长运算�?
运算符说明`#`取长运算�?单目运算�?

`#` 操作符可用于获取字符串长度、或有序数组包含的元素个数�?
- 如果 `#` 操作符用于字符串则返回字符串长度,

- 如果 `#` 操作符用�?[有序数组](../datatype/table/_.html#array)，返回数组长�?\- 该操作符取的是索引自 1 开始的序列数组的长度�?
- 如果 `#` 操作符用�?null 空值则返回 0,


如果用于其他数据类型，则检查对象是否定义了 `_len` 元方法，如果存在 `_len` 元方法就调用 `_len` 元方法返回值，否则抛出异常�?
请特别注意：

1. table,string,null 不能重载 `_len` 元方法�?2. 多线程共享表�?[thread.table](https://www.aardio.com/zh-cn/doc/library-reference/thread/table.html) 对象 ）只是线程共享资源的代理表，所�?`#` 操作符不能获取多线程共享表里数组元素的个数，应当改用 thread.table 对象提供�?len 方法�?length 属性获取多线程共享数组的长度�?3. `#` 不适用�?[稀疏数组](../datatype/table/_.html#sparse-array)�?
aardio 示例�?
```aardio aardio
import console;

var str = "";
if( #str ){
    console.log( "字符串非�?,str );
}
else{
    console.log ( "null 或空�? );
}

console.pause();

```

因为 `#` 操作符对于一个空字符串或 null 值都会返�?0，如果要判断�?null 并非空字符串时，可以使用 # 操作符简化判断语句�?
要特别注�?`#` 只能用来计算 [有序数组](../datatype/table/_.html#array) 的长度�?
如果表中包含�?[稀疏数组](../datatype/table/_.html#sparseArray) \- 也就是说表成员的数值键（索引）包含不连续的、中断的数值，那么不可将获取有序数组长度的 `#` 操作符用于稀疏数组�?
下面的数组就包含�?null 值，属于数值键（索引）不连续的稀疏数组：

```aardio aardio
var array = { "值：1", null, "值：2", "值：4", null, null }

```

null 值就是没有值，所以数组尾部的 null 是无意义的，正确写法如下�?
```aardio aardio
var array = { "值：1", null, "值：2", "值：4" }

```

数组中间�?null 不可省略，但实际�?null 仍然是表示不存在的值，以上数组等价写法如下�?
```aardio aardio
var array = {
    [1] = "值：1";
    [2] = "值：2";
    [4] = "值：4";
}

```

这种稀疏数组可以用 table.range() 获取最小索引、最大索引。也可以使用 table.eachArgs() 遍历稀疏数组�?
示例�?
```aardio aardio
import console.int;
var sparseArray = { "值：1", null, "值：2", "值：4" }

//获取稀疏数组长�?var min,max = table.range(sparseArray);

//遍历稀疏数组（可用于遍历函数的不定参数�?for i,v in table.eachArgs(sparseArray) {
    console.log(i,v)

}

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/language-reference/operator/len.md)

