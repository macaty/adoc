[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鎻掑叆鎺掑簭

```aardio aardio
import console;

//鎻掑叆鎺掑簭绠楁硶
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

//鎻掑叆鎺掑簭绠楁硶 - 鍊掑簭
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
console.log("鎻掑叆鎺掑簭( 鍘熷湴鎺掑簭 )")
console.log("----------------")

array ={12;3;556;7;17788;23};
insertSortDesc(array)

//杈撳嚭缁撴灉
for(i=1;#array;1){
    console.log( array[i] )
}

execute("pause")

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/aardio/Array/ComparisonSort/InsertionSort.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/aardio/Array/ComparisonSort/InsertionSort.md')

