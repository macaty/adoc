[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: COM 鎺ュ彛

```aardio aardio
//COM 鎺ュ彛
import vc6;
var vc = vc6( "/" )

//杈撳叆 C++ 婧愮爜锛岃嚜鍔ㄥ瓨涓?/comMain.cpp
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
   LPDISPATCH pDispatch = ( new CTestObject() )->GetIDispatch(FALSE);//鍙傛暟FALSE鎸囧畾涓嶈娣诲姞寮曠敤璁℃暟
   return pDispatch;
}
******/

//缂栬瘧鐢熸垚DLL
vc.exec(
    'cl comMain.cpp'
    ,'/W3' /*璀﹀憡绛夌骇*/
    ,'/MD' /*浣跨敤澶氱嚎绋嬪姩鎬佽繍琛屽簱*/
    ,'/O2 /Ot /EHsc' /*浠ｇ爜浼樺寲閫夐」*/
    ,'/D "WIN32" /D "_WINDOWS" /D "_MBCS" /D "_USRDLL" /D "_AFXDLL" ' /*瀹氫箟甯告暟鍜屽畯*/
    ,'/I"./INCLUDE"'/*鎸囧畾澶存枃浠剁洰褰?/
    ,'kernel32.lib user32.lib gdi32.lib winspool.lib comdlg32.lib advapi32.lib shell32.lib ole32.lib oleaut32.lib uuid.lib odbc32.lib odbccp32.lib' /*瀵煎叆搴?/
    ,'/link /SUBSYSTEM:WINDOWS /MACHINE:X86' /*鍚庨潰鏄摼鎺ュ弬鏁?*/
    ,'/out:test.disp.dll'/*杈撳嚭鏂囦欢鍚?/
    ,'/dll' /*杈撳嚭DLL*/
    ,'/LIBPATH:".\LIB" /LIBPATH:".\LIB2"' /*鎸囧畾搴撶洰褰?/
)

//鍔犺浇 DLL
var dll = raw.loadDll("/test.disp.dll",,"cdecl");

//鍒涘缓 COM 瀵硅薄锛宎ardio 鍙嚜鍔ㄦ敮鎸?IDispatch 鎺ュ彛
//https://www.aardio.com/zh-cn/doc/library-guide/builtin/com/com.html
import com;
var comObject = com.QueryObjectR( dll.CreateIDispatchObjectP() );

//浣跨敤 COM 瀵硅薄
comObject.name = "娴嬭瘯";
console.log( comObject.name );
console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/CPP/com.IDispatch.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/CPP/com.IDispatch.md')

