[aardio 鏂囨。](../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鎺у埗鍙扮▼搴忚寖渚?- 鍑虹墝

```aardio aardio
//鎺у埗鍙扮▼搴忚寖渚?- 鍑虹墝
import console;

//缁勫悎锛堢瑳鍗″皵绉級
import table.product;
product = function(a,b){
    var t = {};
    for(c in table.product(a,b) )
        table.push(t,c[1] ++ c[2] );

    return t;
}

//娲楃墝锛?鏁扮粍涔卞簭 锛?var cards = table.shuffle( product(
     {"绾㈡"; "鏂瑰潡"; "榛戞"; "姊呰姳"},
     {"A"; "2"; "3"; "4"; "5"; "6"; "7"; "8"; "9"; "10"; "J"; "Q"; "K" }
) );

for( i=1;5 ){
    console.log( table.remove(cards) );//涓嬩竴寮犵墝
    sleep(300);
}

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Console/PlayCards.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Console/PlayCards.md')

