[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 控制台程序范�?- 出牌

```aardio aardio
//控制台程序范�?- 出牌
import console;

//组合（笛卡尔积）
import table.product;
product = function(a,b){
    var t = {};
    for(c in table.product(a,b) )
        table.push(t,c[1] ++ c[2] );

    return t;
}

//洗牌�?数组乱序 �?var cards = table.shuffle( product(
     {"红桃"; "方块"; "黑桃"; "梅花"},
     {"A"; "2"; "3"; "4"; "5"; "6"; "7"; "8"; "9"; "10"; "J"; "Q"; "K" }
) );

for( i=1;5 ){
    console.log( table.remove(cards) );//下一张牌
    sleep(300);
}

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Console/PlayCards.md)

