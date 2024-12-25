[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 使用JS数组

```aardio aardio
//使用JS数组
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=349;bottom=249;scroll=1)
winform.add()
/*}}*/

import web.form;
var wb = web.form( winform );
winform.show();

wb.write("");
wb.wait("");

import console;
wb.external={
    log = function(...){
        console.log(...)
    }
    [1] = "123";
    [2] = "456";
    item = function(index){
        //external不能作为数组使用,
        //所以我们需要自已实现一个接口访问数组成�?        return owner[index+1] //注意aardio下标�?开�?而Javascript�?开�?    }
 }
//在external中直接访问数组成�?var js = /*
    external.log( external.item(1) )
    */
wb.doScript( js );

//======================================================

//枚举aardio对象
var js = /*
    var e = new Enumerator(external);

    for   (;!e.atEnd();e.moveNext()){
        k = e.item();

        if( typeof(k)=="string")
            external.log(k,external[k])
    }
    */
wb.doScript( js );

//======================================================

//将aardio数组转换为JS数组
wb.external.items = function(index){
        return wb.jsArray({123;"aardio数组第二个成�?}) //将aardio数组转换为JS数组
    }

var js = /*
    var aardioArray = external.items();
    external.log( aardioArray[1] )
    */
wb.doScript( js );

//======================================================

//在aardio中使用JS数组对象
wb.external.testJsArray = function(jsArray){

        for(i=1;jsArray.length ){
            io.print( i, jsArray[i-1] )
        }
}

var js = /*
    var jsArray = new Array('abc',123)
    external.testJsArray(jsArray)
    */
wb.doScript( js );

//======================================================

//进入消息循环
win.loopMessage();
io.close();//关闭控制�?
```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/web.form/Script/array.md)

