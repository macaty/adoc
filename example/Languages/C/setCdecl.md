[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: C 璇█璋冪敤 aardio

```aardio aardio
//C 璇█璋冪敤 aardio

import tcc;
var c = tcc();
c.code = /***
    #include <stdio.h>
    #include <windows.h>

    //璇ュ嚱鏁板湪C璇█涓０鏄?鍦╝ardio涓畾涔?    void func_aardio(const wchar_t *u16,const char * u8);

    int main ()
    {
        func_aardio(L"杩欐槸C璇█涓殑Unicode(UTF16)瀛楃涓?,"杩欐槸C璇█涓殑UTF8瀛楃涓?);
        return 1;
    }
***/

//瀹氫箟涓�涓猘ardio鍑芥暟
import win;
aardio_func = function(u16,u8){
    win.msgbox(u16,u8);
}

//瀵煎叆涓篊璇█鍑芥暟瀹氫箟
c.setCdecl(
    aardio_func, //aardio鍑芥暟鍚嶅瓧
    "func_aardio", //鍦–璇█涓皟鐢ㄧ殑鍑芥暟鍚嶅瓧
    "void(ustring u16,str u8)" //鍑芥暟鍘熷瀷,涓嶤璇█涓殑澹版槑蹇呴』涓�鑷?
)

//閾炬帴骞惰繍琛孋璇█main()鍑芥暟
c.run();
c.close();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/C/setCdecl.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/C/setCdecl.md')

