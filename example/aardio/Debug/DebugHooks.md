[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调试钩子

```aardio aardio
import debug;

//注册一个新的调试钩�?var dbg = debug.hook()

//每行代码触发
dbg.line = function(line){

    io.print( "line",line )

    //可用类似sql语法查询调试信息
    var info = debug.queryinfo(2,"select source,function,upvars,name,currentline,activelines");
    io.print( info.name,info.name_where /* ,info.source.code*/ )
}

//调用函数触发
dbg.call = function(){
    io.print( "call" )
    io.print( debug.traceback(,"调用�?,2));
}

//返回值触�?dbg.return = function(line){
    io.print( "return" )
}

//尾调用触�?必须同时定义 dbg.return 回调,如果仅指�?dbg.tailreturn 则不会被触发
dbg.tailreturn = function(line){
    io.print( "tailreturn" )
}

io.open()
function func(){

}
func()
io.print("aaa")

dbg.line = null; //注销一个钩子函�?dbg.call = null; //注销一个钩子函�?dbg.return = null; //注销一个钩子函�?dbg.tailreturn = null; //注销一个钩子函�?
execute("pause")

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/aardio/Debug/DebugHooks.md)

