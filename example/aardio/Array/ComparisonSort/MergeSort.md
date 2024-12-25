[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 合并排序

```aardio aardio
import console;

var merge = function(array,from,mid,to){

    var left = { table.unpack(array,from,mid) }
    var right = { table.unpack(array,mid+1,to) };

    var i = 1;
    var j = 1;

    for(k=from;to){
        //比较left,right最前面的一个数,从中取最小的一�?        if( (!right[j]) or left[i] <= right[j] ){
            //如果right�?�?right[j]为真,就直接取left
            array[k] = left[i];
            i++;
        }
        else {
            //如果L�?则left[i]为null,null不会小于等于任何�?left[i] <= right[j]必然为不成立
            array[k] = right[j];
            j++;
        }
    }

}

var mergeSort;
mergeSort = function(array,from,to) {

    if( from < to ){
        var mid =math.floor( ( from + to ) / 2)
        mergeSort(array,from,mid);
        mergeSort(array,mid+1,to);
        merge(array,from,mid,to);
    }
}

console.log("----------------")
console.log("合并排序( 基于分治�?)")
console.log("----------------")

array ={2;4;5;7;1;2;3};
mergeSort(array,1,#array)

//输出结果
for(i=1;#array;1){
    console.log( array[i] )
}

execute("pause")

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/aardio/Array/ComparisonSort/MergeSort.md)

