[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 C 璇█涔?main 鍑芥暟

```aardio aardio
//aardio 璋冪敤 C 璇█涔?main 鍑芥暟
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

//鐩存帴杩愯 main() 鍏ュ彛鍑芥暟
var ret = c.run("娓│鍛戒护鍙冩暩","娓│鍛戒护鍙冩暩2","鏀寔浠绘剰澶氬�嬪弮鏁?);
console.print( ret )

c.close();
console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/C/run_main.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/C/run_main.md')

