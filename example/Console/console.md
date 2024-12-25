[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 控制台程�?- 入门

```aardio aardio
//控制台程�?- 入门
import console;

console.log("console 库函数大多可以自动打开控制�?)
if(_WIN10_LATER){
    console.log("Win10 以上系统支持�?Alt + Enter 切换全屏");

    //全屏
    console.fullscreen();
}

console.box(,,60,10,31,"请输入文�?" )
var str = console.getText( "请输入文�?" )

console.clearScreen ();//清屏
var num = console.getNumber( "请输入数�?" ); //输入错误数值自动重�?var arr = { str;num }

//输出变量到控制台
console.varDump( arr )

//输出变量到控制台
console.dump( arr )

//以JSON格式输出变量到控制台
console.dumpJson( arr )

//将控制台窗口的文本再读到字符串中
str = console.readOutputCharacter()
console.log( "--------------------------" )
console.log( str )

for(i=1;25;1){
    console.printf("%d -> 20",i );
    console.more( 10 ); //分页显示
}

console.pause()

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Console/console.md)

