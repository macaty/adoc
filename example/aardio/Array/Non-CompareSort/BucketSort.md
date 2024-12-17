[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 桶排�?
```aardio aardio
import console;

/*
桶排序假设输入元素均匀而独立分布在区间[0,1) �? 0 <= x and x < 1;
将区间划分成n个相同大小的子区�?�?,然后将n个输入按大小分布到各个桶中去,对每个桶内部进行排序�?最后将所有桶的排序结果合并起�?
*/

//插入排序算法
var insertSort = function( array ){

    for( right=2;#array ) {
        var top = array[right];

        //Insert array[right] into the sorted seqquence array[1....right-1]
        var left = right -1;
        while( left and array[left]>top){
            array[left+1] = array[left];
            left--;
        }
        array[left+1] = top;

    }
    return array;
}

//桶排序算�?var bucketSort = function( array ){
    var n = #array;

    var bucket ={}
    for(i=0;n;1){
        bucket[i] = {} //创建一个桶
    }

    var bucket_index
    for(i=1;n;1){
        bucket_index =  math.floor(n * array[i]);
        table.push( bucket [ bucket_index ],array[i] );//放到桶里�?    }

    for(i=1;n;1){
        insertSort( bucket[i] ); //对每个桶进行插入排序
    }

    return table.concat( table.unpack(bucket) );

}

console.log("----------------");
console.log("桶排�?);
console.log("----------------");

var array={};

//桶排序假设输入是由一个随机过程产生的小数
for(i=1;20;1){
    table.push( array,math.random() );
}

//排序
array = bucketSort( array );

//输出结果
for(i=1;#array;1){
    console.log( array[i] );
}

execute("pause");

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/aardio/Array/Non-CompareSort/BucketSort.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/aardio/Array/Non-CompareSort/BucketSort.md')

