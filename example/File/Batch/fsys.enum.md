[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 遍历文件

```aardio aardio
//遍历文件
import console;
import fsys;

//请选择要遍历的目录
var rootDir = "~\lib\fsys";

//批量处理文件
fsys.enum( rootDir, //指定
    "*.*", //指定查询文件�?支持通配�?也可以用一个数组指定多个查询文件名
    function(dirname,filename,fullpath,findData){
        //可使�?return false 退出枚举过�?
        if(filename){
            console.log("发现文件�?,filename )
            console.log("完整路径",fullpath )

            /*
            可以�?fsys.replace 函数替换文件内容,
            fsys.replace(fullpath,"查找的内容\d+","替换的内�?,替换次数)

            fsys.replace 支持二进制文件或 UTF-8 文本文件�?            其他编码�?fsys.codepage 加载文件后用 string.replace() 函数替换�?            或者用 fsys.batch 实现批量处理并且支持自动处理编码转换�?            */
        }
        else{
            console.log("发现目录�?,dirname)
        }
    } ,/*如果此参数为false则忽略子目录*/
);

console.log( "临时目录",fsys.getTempDir() );
console.log( "桌面目录",io.getSpecial( 0 /*_CSIDL_DESKTOP*/  ) );
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/Batch/fsys.enum.md)

