[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鍐呭瓨璋冪敤 Rust DLL

```aardio aardio
//aardio 鍐呭瓨璋冪敤 Rust DLL
import fsys;
import process.rust;
import process.vswhere;
import console;

/*
Rust 蹇�熷叆闂細
https://quickref.me/zh-CN/docs/rust.html
https://learnxinyminutes.com/docs/zh-cn/rust-cn/
*/
var vswhere = process.vswhere("-latest -requires Microsoft.VisualStudio.Component.VC.Tools.x86.x64");
if(!#vswhere){
    console.log("杩愯 Rust 缂栬瘧鍣ㄥ繀椤诲厛瀹夎 VC++ 2017 鎴?2019");
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
    console.pause(,"鎸変换鎰忛敭鐢?aardio 璋冪敤 Rust 鐢熸垚鐨?DLL缁勪欢")

    //DLL 宸茬粡閰嶇疆涓轰笉渚濊禆 VC++ 杩愯搴?    //娉ㄦ剰榛樿涓篶decl璋冪敤绾﹀畾,鍦―LL璺緞鍓嶅姞涓?绗﹀彿灏辨槸鍔犺浇涓哄唴瀛楧LL锛堜笉鍐嶉渶瑕丏LL鏂囦欢锛?    var dll = raw.loadDll("\rust_dll\target\i686-pc-windows-msvc\release\rust_dll.dll",,"cdecl");

    //aardio 涓暣鍨嬪ぇ鍐欒〃绀烘棤绗﹀彿鏁?    var info ={
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
    鐩稿叧鏂囨。锛?https://www.aardio.com/zh-cn/doc/library-guide/builtin/raw/directCall.html
    鐩稿叧鑼冧緥锛氥�?aardio 鑼冧緥 / 璋冪敤鍏朵粬璇█ / C璇█ 銆?    */
    var ret = dll.hello_rust("Hello,Rust!",buf,info);

    console.dumpJson(info)
    console.log( info.arr[4] ) // -> 19
    console.log( "buf:",buf)
    console.log("ret:",ret)
    console.pause()
}

console.pause()

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Rust/dll.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Rust/dll.md')

