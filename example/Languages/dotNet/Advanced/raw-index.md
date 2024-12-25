[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?aardio 中扩�?.NET 对象

```aardio aardio
//�?aardio 中扩�?.NET 对象
import console.int;
import dotNet;

//引入 .Net 类（这里也可以直接改�?import System�?dotNet.import("System");

/*
导入�?.NET 类如果定义名�?"ctor(...)" 的扩展构造函数�?则该函数将在 aardio 构�?.NET 类之前执行�?*/
System.Uri[["ctor(...)"]] = function(netCtor,url,...){

    //在这里可以改动、检测构造参�?    if(!url) error("参数 @1 请指定网址",3);

    //调用真实的构造函�?netCtor 创建对象，该函数成功返回对象，失败返�?null,错误信息
    var obj,err = netCtor(url,...); //返回新的构造参�?
    //返回创建的对�?    return obj,err;
}

/*
�?aardio 中实例化 .NET 类以后，
可自动调用名�?"ctor" 的扩展构造参数（不能拦截构造参数，也不需要返回值）�?这个函数的参数就是已经创建的 .NET 对象实例�?*/
System.Uri[["ctor"]] = function(this){ //this 参数为已创建�?.NET 对象实例

    /*
    aardio 读写 .NET 对象的成员会触发对象元方法并转换�?.NET 调用�?    如果改用直接下标 [[]] 就可直接读写对象的成员，不会触发元方法也不会解析�?.NET 调用�?    */
    this[["getHostAndHashCode"]] = function(){
        return owner.Host,owner.GetHashCode();
    }
}

//�?aardio 代码内调�?System.Uri() 创建 .NET 对象会调�?aardio 扩展的构造函数�?var uri = System.Uri("https://www.aardio.com/test?q=aardio")

//调用 .NET 对象实例的成员函�?console.log( uri.getHostAndHashCode() );

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Advanced/raw-index.md)

