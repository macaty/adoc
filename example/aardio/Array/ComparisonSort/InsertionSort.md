[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 插入排序

```aardio aardio
import console;

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

//插入排序算法 - 倒序
var insertSortDesc = function( array ){

    for( right=2;#array ) {
        var top = array[right];

        //Insert array[right] into the sorted seqquence array[1....right-1]
        var left = right -1;
        while( left and array[left]<top){
            array[left+1] = array[left];
            left--;
        }
        array[left+1] = top;

    }
    return array;
}

console.log("----------------")
console.log("插入排序( 原地排序 )")
console.log("----------------")

array ={12;3;556;7;17788;23};
insertSortDesc(array)

//输出结果
for(i=1;#array;1){
    console.log( array[i] )
}

execute("pause")

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/aardio/Array/ComparisonSort/InsertionSort.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/aardio/Array/ComparisonSort/InsertionSort.md')
