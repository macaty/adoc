[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 计数排序

```aardio aardio
import console;

/*
假设 n �?0 �?k 之间的整数�?对于每一个输入元�?x ,确定出小�?x 的元素个�?lt ,�?x 可直接放于输出位�?lt + 1 上�?*/

//计数排序算法
var countingSort = function( array ,k){
    array_sorted ={};

    count ={};
    for(i=0;k ){
      count[i] = 0;
    }

    for(i=1;#array;1){
        count[ array[i] ] = count[ array[i] ] + 1; //count[n] 包含等于n的个�?
    }

    //统计位置
    for(i=1;k;1){
        count[i] += count[i-1]; //count[i] 包含小于等于i的个�?    }

    var n;
    for(i=#array;1;-1){
        n = array[i]
        array_sorted[ count[n] ] = n;
        count[n]--;//防止相同的元素n再次出现,将计数减一
    }

    return array_sorted;
}

console.log("----------------")
console.log("计数排序( 线性时间排�?)")
console.log("----------------")

var array = {12;3;22;7;6;23;26};

//取出最大的�?var max = math.max( table.unpack(array) ) ;

//排序
array = countingSort(array,max  )

//输出结果
for(i=1;#array;1){
    console.log( array[i] )
}

execute("pause")

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/aardio/Array/Non-CompareSort/CountingSort.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/aardio/Array/Non-CompareSort/CountingSort.md')

