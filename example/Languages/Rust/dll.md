[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 内存调用 Rust DLL

```aardio aardio
//aardio 内存调用 Rust DLL
import fsys;
import process.rust;
import process.vswhere;
import console;

/*
Rust 快速入门：
https://quickref.me/zh-CN/docs/rust.html
https://learnxinyminutes.com/docs/zh-cn/rust-cn/
*/
var vswhere = process.vswhere("-latest -requires Microsoft.VisualStudio.Component.VC.Tools.x86.x64");
if(!#vswhere){
    console.log("运行 Rust 编译器必须先安装 VC++ 2017 �?2019");
    console.pause();

    process.execute("https://visualstudio.microsoft.com/downloads/")
    return;
}

process.rust.workdir = "/"

console.open()
if(!io.exist("/rust_dll")){
    process.rust.createDllProject("rust_dll")

    /*
    import process.code;
    process.code.install();
    process.code("/rust_aardio_dll");
    */
}

process.rust.workDir = "/rust_dll"
if(process.rust.build()){
    console.pause(,"按任意键�?aardio 调用 Rust 生成�?DLL组件")

    //DLL 已经配置为不依赖 VC++ 运行�?    //注意默认为cdecl调用约定,在DLL路径前加�?符号就是加载为内存DLL（不再需要DLL文件�?    var dll = raw.loadDll("\rust_dll\target\i686-pc-windows-msvc\release\rust_dll.dll",,"cdecl");

    //aardio 中整型大写表示无符号�?    var info ={
        byte i8,
        word i16,
        int i32,
        long i64,
        BYTE u8,
        WORD u16,
        INT u32,
        LONG u64,
        double f64;
        int arr[4] = {1,2,3,4};
    }

    var buf = raw.buffer(100);

    /*
    相关文档�?https://www.aardio.com/zh-cn/doc/library-guide/builtin/raw/directCall.html
    相关范例：�?aardio 范例 / 调用其他语言 / C语言 �?    */
    var ret = dll.hello_rust("Hello,Rust!",buf,info);

    console.dumpJson(info)
    console.log( info.arr[4] ) // -> 19
    console.log( "buf:",buf)
    console.log("ret:",ret)
    console.pause()
}

console.pause()

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Rust/dll.md)

