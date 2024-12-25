[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: COM 接口

```aardio aardio
//COM 接口
import vc6;
var vc = vc6( "/" )

//输入 C++ 源码，自动存�?/comMain.cpp
vc.comMain  = /******
#include <afxwin.h>
#include <afxdisp.h>

class CTestObject: public CCmdTarget
{
    DECLARE_DYNCREATE(CTestObject)
    CTestObject();
protected:
    virtual ~CTestObject();
    CString strName;
public:
    afx_msg BSTR GetName();
    afx_msg void SetName(LPCTSTR lpszName);
    DECLARE_DISPATCH_MAP()
};

IMPLEMENT_DYNCREATE(CTestObject, CCmdTarget)
CTestObject::CTestObject() {
    EnableAutomation();
    AfxOleLockApp();
}
CTestObject::~CTestObject() {
    AfxOleUnlockApp();
}

BEGIN_DISPATCH_MAP(CTestObject, CCmdTarget)
    DISP_PROPERTY_EX(CTestObject, "name", GetName, SetName, VT_BSTR)
END_DISPATCH_MAP()

BSTR CTestObject::GetName()
{
     return strName.AllocSysString();
}

void  CTestObject::SetName(LPCTSTR lpszName)
{
    strName = lpszName;
}

extern "C" __declspec(dllexport) LPDISPATCH __cdecl CreateIDispatchObject() {
   LPDISPATCH pDispatch = ( new CTestObject() )->GetIDispatch(FALSE);//参数FALSE指定不要添加引用计数
   return pDispatch;
}
******/

//编译生成DLL
vc.exec(
    'cl comMain.cpp'
    ,'/W3' /*警告等级*/
    ,'/MD' /*使用多线程动态运行库*/
    ,'/O2 /Ot /EHsc' /*代码优化选项*/
    ,'/D "WIN32" /D "_WINDOWS" /D "_MBCS" /D "_USRDLL" /D "_AFXDLL" ' /*定义常数和宏*/
    ,'/I"./INCLUDE"'/*指定头文件目�?/
    ,'kernel32.lib user32.lib gdi32.lib winspool.lib comdlg32.lib advapi32.lib shell32.lib ole32.lib oleaut32.lib uuid.lib odbc32.lib odbccp32.lib' /*导入�?/
    ,'/link /SUBSYSTEM:WINDOWS /MACHINE:X86' /*后面是链接参�?*/
    ,'/out:test.disp.dll'/*输出文件�?/
    ,'/dll' /*输出DLL*/
    ,'/LIBPATH:".\LIB" /LIBPATH:".\LIB2"' /*指定库目�?/
)

//加载 DLL
var dll = raw.loadDll("/test.disp.dll",,"cdecl");

//创建 COM 对象，aardio 可自动支�?IDispatch 接口
//https://www.aardio.com/zh-cn/doc/library-guide/builtin/com/com.html
import com;
var comObject = com.QueryObjectR( dll.CreateIDispatchObjectP() );

//使用 COM 对象
comObject.name = "测试";
console.log( comObject.name );
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/CPP/com.IDispatch.md)

