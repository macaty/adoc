[aardio 鏂囨。](../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鎺у埗鍙扮▼搴?- 鍏ラ棬

```aardio aardio
//鎺у埗鍙扮▼搴?- 鍏ラ棬
import console;

console.log("console 搴撳嚱鏁板ぇ澶氬彲浠ヨ嚜鍔ㄦ墦寮�鎺у埗鍙?)
if(_WIN10_LATER){
    console.log("Win10 浠ヤ笂绯荤粺鏀寔鎸?Alt + Enter 鍒囨崲鍏ㄥ睆");

    //鍏ㄥ睆
    console.fullscreen();
}

console.box(,,60,10,31,"璇疯緭鍏ユ枃鏈?" )
var str = console.getText( "璇疯緭鍏ユ枃鏈?" )

console.clearScreen ();//娓呭睆
var num = console.getNumber( "璇疯緭鍏ユ暟鍊?" ); //杈撳叆閿欒鏁板�艰嚜鍔ㄩ噸璇?var arr = { str;num }

//杈撳嚭鍙橀噺鍒版帶鍒跺彴
console.varDump( arr )

//杈撳嚭鍙橀噺鍒版帶鍒跺彴
console.dump( arr )

//浠SON鏍煎紡杈撳嚭鍙橀噺鍒版帶鍒跺彴
console.dumpJson( arr )

//灏嗘帶鍒跺彴绐楀彛鐨勬枃鏈啀璇诲埌瀛楃涓蹭腑
str = console.readOutputCharacter()
console.log( "--------------------------" )
console.log( str )

for(i=1;25;1){
    console.printf("%d -> 20",i );
    console.more( 10 ); //鍒嗛〉鏄剧ず
}

console.pause()

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Console/console.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Console/console.md')

