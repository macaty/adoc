[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 交换排序

```aardio aardio
import console;

/*-------------------------------------------------------
 * 冒泡排序
 *-------------------------------------------------------*/

//冒泡排序实现简�?代码较少,是较常用交换类排�?bubbleSort = function(arr) {
    for( i=1;#arr) {
        for(j=#arr;i+1;-1) //自后向前挨个比较,i前面的已经是最小的�?并排序好�?            if(arr[j]<arr[j-1]) //小的总是往前排
                arr[j],arr[j-1] = arr[j-1],arr[j];
    }
}

console.log("冒泡排序( 交换类换排序 )")
console.log("---------------------------")

var arr = {2;46;5;17;1;2;3;99;12;56;66;21};
bubbleSort(arr,1,#arr)

//输出结果
console.dump(arr)
console.more(1)

/*
 *-------------------------------------------------------
 * 快速排�? *-------------------------------------------------------*/

console.log("快速排�? 交换类排�?基于分治�?)")
console.log("---------------------------")

parttion = function(arr,from,to){
    var x = arr[to];//选定主元(pivot element)

    var left = from-1;
    for(j=from;to-1){
        if(arr[j]<=x){ //如果比主元小
            left++;
            arr[j],arr[left]  = arr[left],arr[j]; //互换,小的去左�?        }
    }

    //主元移中�?    var pivot = left+1;
    arr[pivot],arr[to]  = arr[to],arr[pivot];
    return pivot;
}

//快速排序的随机版本
ranParttion = function(arr,from,to){
    var pivot = math.random(from,to);
    arr[pivot],arr[to] = arr[to],arr[pivot];
    return parttion(arr,from,to)
}

quickSort = function(arr,from,to){
    if(from<to){
        //小的站pivot左边,大的站pivot右边
        var pivot = ranParttion(arr,from,to)
        quickSort(arr,from,pivot-1);
        quickSort(arr,pivot+1,to);
    }

}

var arr ={2;46;5;17;1;2;3;99;12;56;66;21};
quickSort(arr,1,#arr);

//输出结果
console.dump(arr);
console.more(1);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/aardio/Array/ComparisonSort/ExchangeSort.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/aardio/Array/ComparisonSort/ExchangeSort.md')

