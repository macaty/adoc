[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 编译 DLL

```aardio aardio
//编译 DLL
import process.gfortran;

//创建 gfortran 编译环境，参数指定工作目录，单个斜杠或反斜杆表示应用程序根目录（工程目录、或工程外独立启动文件所在目录，发布后为 EXE 目录�?var fortran = process.gfortran("/");

/*
在工作目录下保存为同名源码文件，
也可以写�?fortran["main.f95"] 显式指定后缀名（可使�?f90,f95,f03 等后缀名）�?
Fortran 忽略大小�?Fortran 参数默认是传址的（传指针）
Fortran 快速入�? https://learnxinyminutes.com/docs/zh-cn/fortran95-cn/
*/
fortran.main = /*
module test
!引入支持C语言类型的模块，不能写在 DLLEXPORT 后面  https://gcc.gnu.org/onlinedocs/gfortran/ISO_005fC_005fBINDING.html
use iso_c_binding  !Fortran 2003 特�?
type, bind(c) :: POINT
  integer(c_int) :: x
  integer(c_int) :: y
end type POINT

CONTAINS

integer function Add (a,b)
    !声明�?DLL 导出函数，关键是下面这句，调用约定建议用 CDECL，最后面的函数名要一�?    !GCC$ ATTRIBUTES CDECL,DLLEXPORT ::Add

    !Fortran 默认是传址的，所�?integer 实际上是相当于C语言�?int 指针�?    integer  :: a
    integer :: b
    Add = a + b
END  function

integer(c_int) function AddByVal(i,j,d)
    !GCC$ ATTRIBUTES CDECL,DLLEXPORT ::AddByVal  !声明�?DLL 导出函数

    !声明�?C语言 int 类型，VALUE 的意思是传�?    integer(c_int), VALUE :: i
    integer(c_int), VALUE :: j
    real(c_double), VALUE :: d
    AddByVal = i + j
end  function

integer(c_int) function AddByPoint(pt)
    !GCC$ ATTRIBUTES CDECL,DLLEXPORT ::AddByPoint
    type(POINT) :: pt

    ! Fortran 里用 % 号访问成员（类似 aardio 里的 . 符号�?    AddByPoint = pt%x + pt%y
end  function

integer(c_int) function hello(str,len)
    !GCC$ ATTRIBUTES CDECL,DLLEXPORT ::hello
    CHARACTER*(*) :: str
    integer(c_int), VALUE ::  len

    !重新绑定控制�?    close (unit=6)
    open(unit=6,file='CONOUT$')

    !输出字符�?    print "(a)",str(1:len)
    hello = len
end  function

integer function TestArray(arr,len)
    !GCC$ ATTRIBUTES CDECL,DLLEXPORT ::TestArray
    integer(c_int), VALUE :: len
    integer i, arr(len)
    integer total

    total = 0
    do i = 1,len
        total = total + arr(i)
    end do

    arr(1) = 123
    TestArray = total
end  function

end module test
*/

fortran.buildShared("-o fortran.dll main.f95");

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Fortran/buildShared.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Fortran/buildShared.md')

