[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 AutoCAD - .NET 鎺ュ彛

```aardio aardio
//aardio 璋冪敤 AutoCAD - .NET 鎺ュ彛
import console;
console.showLoading("姝ｅ湪缂栬瘧 .NET DLL");

import dotNet;
import com.cad;
var cad = com.cad();
cad.Visible = true;

//鍒涘缓 C# 璇█缂栬瘧鍣紙AutoCAD 2025 鍙婁箣鍚庣増鏈鏀圭敤 VS 缂栬瘧锛?var compiler = cad.NetCompiler("C#");

//璁剧疆寰呯紪璇慍#婧愮爜锛?娉ㄩ噴鍙祴鍊间负瀛楃涓诧紝娉ㄩ噴鏍囪棣栧熬鏄熷彿鏁扮洰瑕佷竴鑷?锛?//鏀寔妯℃澘璇硶锛?https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.html
compiler.Source = /******
using System;
using System.Collections.Generic;
using System.Text;
using Autodesk.AutoCAD.ApplicationServices;
using Autodesk.AutoCAD.DatabaseServices;
using Autodesk.AutoCAD.Runtime;
using Autodesk.AutoCAD.Windows;
using Autodesk.AutoCAD.EditorInput;

public class TestCAD
{
         [LispFunction("aardioTestNetApi")]
         public static ResultBuffer TestNetApi(ResultBuffer lspArgs)
         {
             ResultBuffer lspRet = new ResultBuffer();
             if (lspArgs == null) return null;

             TypedValue[] args = lspArgs.AsArray();
             try
             {
                 if (args.Length == 2)
                 {
                     string a = args[0].Value as string;
                     string b = args[1].Value as string;

                     lspRet.Add(new TypedValue((int)LispDataType.Text, a + b));
                 }
             }
             catch (Autodesk.AutoCAD.Runtime.Exception)
             {
                 return null;
             }
              return lspRet;
         }

}

******/

//缂栬瘧骞惰繑鍥炵▼搴忛泦
var assembly = compiler.CompileOrFail("/aardioTestNetApi.dll");

//鍔犺浇 C# 鐢熸垚鐨?DLL
cad.NetLoad("/aardioTestNetApi.dll");
cad.NetLoad(
//璋冪敤 .NET 鍒涘缓鐨?LISP 鍑芥暟
cad.SendCommand(`(aardioTestNetApi "abc" "def")`);
cad.ShowForeground();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/AutoCAD/netload.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/AutoCAD/netload.md')

