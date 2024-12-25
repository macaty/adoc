[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 C 语言函数

```aardio aardio
//aardio 调用 C 语言函数
import console;
import tcc;

var c = tcc();
c.enableIoPrintf(); //启用 io_print 函数

c.code = /****
    #include <stdio.h>
    #include <stdlib.h>

    //C99 __VA_ARGS__ 默认至少匹配1个参�?匹配0个参数时,需要用 ## 去掉前面的逗号
    #define dprintf(level, ...) io_printf(__VA_ARGS__)

    typedef struct {
        int x;
        int y;
    }  Point;

    int helloW (char a,int b, unsigned long long c,Point * ppt,Point pt,double * pd)
    {
        io_printf("C语言接收到参�?a: %d b:%d c: %llu ppt->x: %d ppt->y:%d pt.x: %d pt.y:%d pd:%g\n",a,b,c,ppt->x,ppt->y,pt.x,pt.y,*pd);

        int n = 10;//变量声明可以放函数中�?        long long ln = 100;//64位整�?也就是aardio中的long),C99
        char s[n]; //变长数组,C99 VLA

        //C99标准引入了Designated Initializers特性使得数组、结构体和联合体的初始化更加灵活和方便�?        struct { int x, y; } st[10] = { [0].x = 1, [0].y = 2 };
        int tab[10] = { 1, 2, [5] = 5, [9] = 9};

        //C99 compound literal
        int *p = (int []){ 1, 2, 3 };

        //GCC 数组初始�?        struct { int x, y; } st2 = { x: 1, y: 1};
        struct { int x, y; } st3 = { .x = 1, .y = 1};

        //GCC case ranges
        int v = 2;
        switch(v) {
            case 1 ... 9:
                io_printf("range 1 to 9\n");
                break;
            default:
                io_printf("unexpected\n");
                break;
        }

        //GCC __attribute__语句
        int a2 __attribute__ ( ( aligned(8) ) );
        //参�? https://bellard.org/tcc/tcc-doc.html

        return 0;
    }

****/

//声明C函数，与声明 API 类似
//https://www.aardio.com/zh-cn/doc/library-guide/builtin/raw/api.html
var helloW = c.getCdecl("helloW","void(byte a,int b,LONG c,struct ppt,int pt_x,int pt_y,double &pd)")
helloW(1,2,3,{int x = 4;int y = 5},6,7,8.1);

//也可以不声明，直接调用C函数，与直接调用 API 的规则相�?var ret,ppt,pd = c.helloW(
    1,//小于32位的整型数值可以直接传递，自动兼容
    2,//32位整型数值可以直接传�?自动兼容
    math.size64(3), //无符�?4位整数，可以�?math.size64 对象
    {int x = 4;int y = 5}, //aardio 在API参数中传结构体，总是传结构体指针,
    6,7, //直接在参数中用结构体传值极其罕见，类似这种字段�?2位长的结构体字段可以直接展开为多个参�?    {double v = 8.1} //对等C中的 double * 这种指针，在 aardio 中转换为同类型的结构体指针即�?);
console.log( "C函数返回�?, ret )

/*
如果C函数的参数使用了 double,float 等浮点数值参数（传值，而不是使用指针传址），
则必须先声明再调用，不声明直接调用无法支持这类参数�?
相关文档�?https://www.aardio.com/zh-cn/doc/library-guide/builtin/raw/directCall.html
*/

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/C/getCdecl.md)

