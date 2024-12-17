[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 DLL

```aardio aardio
//调用 DLL
import console

//加载 DLL , DLL 路径前加 $ 实现内存加载 DLL(发布后不需要外�?DLL 文件)
var dll = raw.loadDll($"/fortran.dll",,"cdecl");

/*
不声明直接调用，结构体默认传址，这不用改什么�?生成的函数名�?「aardio 工具 / 探测�?/ DLL 查看工具�?看一下就明白了，前面加模块名，函数名全转小写�?*/
var c = dll.__test_MOD_addbypoint({
    int x = 22;
    int y = 3;
})
console.log(c);

/*
Fortran 中的 integer 相当�?aardio 中的 int 类型�?2位，可用 raw.int() 函数创建，或�?API 中声明为 int 类型�?Fortran 中的 integer*1 相当�?aardio 中的 byte 类型�?位，可用 raw.byte() 函数创建，或�?API 中声明为 byte 类型�?Fortran 中的 integer*2 相当�?aardio 中的 word 类型�?6位，可用 raw.word() 函数创建，或�?API 中声明为 word 类型�?Fortran 中的 real(C_FLOAT), 相当�?aardio 中的 float 类型�?2位，可用 raw.float() 函数创建，或�?API 中声明为 float 类型�?Fortran 中的 real(c_double), 相当�?aardio 中的 double 类型�?4位，可用 raw.double() 函数创建，或�?API 中声明为 double 类型�?https://gcc.gnu.org/onlinedocs/gfortran/ISO_005fC_005fBINDING.html
*/

//可以先声明一下，参数类型加上&声明为按引用传址（指针）
var add = dll.api("__test_MOD_add","int(int &a,int &b)")
var c = add(33,2); //Fortran 的数值参数默认都是传址（传指针�?
//不声明直接调用可以用结构体取代指�?var c = dll.__test_MOD_add({int a=33},{int b=2});

//�?raw.int 创建传址数值也可以
var c = dll.__test_MOD_add(raw.int(33,true),raw.int(2,true));

//参数声明为传值时调用更简单，不声明调用时数值默认为 int 类型
var c = dll.__test_MOD_addbyval(33,2,raw.double(123));
console.log(c);

//字符�?var str = "hello"; //只读字符串，改用 raw.buffer 创建可读写字节数�?dll.__test_MOD_hello(str,#str); //注意到字符串长度传过�?
//数组
var array = {1,2,3}
var c,cArray = dll.__test_MOD_testarray({int items[]=array},#array); //注意到字符串长度传过�?console.log(c);
console.log(cArray.items[1]); //不声明直接调 API，结构体都会在返回值返�?
console.pause(true);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Fortran/loadDll.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Fortran/loadDll.md')

