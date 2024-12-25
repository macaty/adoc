[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 GCC �?Makefile

```aardio aardio
//aardio 调用 GCC �?Makefile
import process.gcc;

//在下面的参数中指�?Makefile 文件所在目�?var gcc = process.gcc("/");

/*

//也可以如下创�?Makefile 文件
gcc.makefile = /**********
hello:
    @echo "Hello, World"
**********/

*/

//执行 make 命令，第一个命令行参数可以指定 gcc.exe 同目录下�?EXE 文件�?gcc.exec("make");

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/GCC/makefile.md)

