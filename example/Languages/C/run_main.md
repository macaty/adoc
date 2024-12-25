[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 C 语言�?main 函数

```aardio aardio
//aardio 调用 C 语言�?main 函数
import console;
import tcc;

var c = tcc();
c.enableIoPrintf();

c.code = /**
    #include <stdio.h>

    int main (int argc, char *argv[])
    {
        int i = 0;
        for( i=1;i<argc;i++){
            io_printf( "%s \n" , argv[i] );
        }

        return 0;
    }
**/

//直接运行 main() 入口函数
var ret = c.run("測試命令參數","測試命令參數2","支持任意多個參�?);
console.print( ret )

c.close();
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/C/run_main.md)

