[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?
```aardio aardio
//�?import console;
/*
table（表）是 aardio 中唯一的复合数据类型，
除了非复合的基础数据类型以外，aardio 中几乎所有的复合对象都是表�?表可以容纳其他的数据成员，也可以嵌套包含其他的表�?https://www.aardio.com/zh-cn/doc/language-reference/datatype/table/_.html
*/

/*
aardio 中的表是哈希表（hashtable），
哈希表使用哈希算法存取，无序正是哈希表的最大优点（索引快如闪电）�?遍历哈希表的顺序并不一定会保持代码中书写的顺序�?*/
var tab = {
    c = "3";
    b = "2";
    a = "1";
}

/*
如果表中不定个数的成员的“键”是�?开始、有序、连续的数值，
那么这些成员构成一个有序数组�?
表总是可以同时包含数组、以及非数组成员�?即使表不包含数组成员，我们也可以将表作为空数组处理�?
在创建数组时，数组的�?又称为“下标”或“索引�?可以省略不写�?*/
var keys = {
    "c","b","a"
}

//用有序的数组排序
for(i,k in keys){
    //用无序的哈希表快速查找�?    console.log(k,tab[k]);
}
console.more(1);

//用有序的数组排序
table.sort(keys);

//用有序的数组排序
for(i,k in keys){
    //用无序的哈希表快速查找�?    console.log(k,tab[k]);
}

console.pause(true);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/aardio/Array/table.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/aardio/Array/table.md')

