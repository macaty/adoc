[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: C 语言调用 aardio

```aardio aardio
//C 语言调用 aardio

import tcc;
var c = tcc();
c.code = /***
    #include <stdio.h>
    #include <windows.h>

    //该函数在C语言中声�?在aardio中定�?    void func_aardio(const wchar_t *u16,const char * u8);

    int main ()
    {
        func_aardio(L"这是C语言中的Unicode(UTF16)字符�?,"这是C语言中的UTF8字符�?);
        return 1;
    }
***/

//定义一个aardio函数
import win;
aardio_func = function(u16,u8){
    win.msgbox(u16,u8);
}

//导入为C语言函数定义
c.setCdecl(
    aardio_func, //aardio函数名字
    "func_aardio", //在C语言中调用的函数名字
    "void(ustring u16,str u8)" //函数原型,与C语言中的声明必须一�?
)

//链接并运行C语言main()函数
c.run();
c.close();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/C/setCdecl.md)

