[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鍚堝苟鎺掑簭

```aardio aardio
import console;

var merge = function(array,from,mid,to){

    var left = { table.unpack(array,from,mid) }
    var right = { table.unpack(array,mid+1,to) };

    var i = 1;
    var j = 1;

    for(k=from;to){
        //姣旇緝left,right鏈�鍓嶉潰鐨勪竴涓暟,浠庝腑鍙栨渶灏忕殑涓�涓?        if( (!right[j]) or left[i] <= right[j] ){
            //濡傛灉right绌?鍒?right[j]涓虹湡,灏辩洿鎺ュ彇left
            array[k] = left[i];
            i++;
        }
        else {
            //濡傛灉L绌?鍒檒eft[i]涓簄ull,null涓嶄細灏忎簬绛変簬浠讳綍鏁?left[i] <= right[j]蹇呯劧涓轰笉鎴愮珛
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
console.log("鍚堝苟鎺掑簭( 鍩轰簬鍒嗘不娉?)")
console.log("----------------")

array ={2;4;5;7;1;2;3};
mergeSort(array,1,#array)

//杈撳嚭缁撴灉
for(i=1;#array;1){
    console.log( array[i] )
}

execute("pause")

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/aardio/Array/ComparisonSort/MergeSort.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/aardio/Array/ComparisonSort/MergeSort.md')

