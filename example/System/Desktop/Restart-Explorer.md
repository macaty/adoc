[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: RUNAS// 淇妗岄潰鍥炬爣

```aardio aardio
//RUNAS// 淇妗岄潰鍥炬爣

import fsys;
import process;

//淇妗岄潰鍥炬爣绌虹櫧
var explorerPath = process.kill("explorer.exe")
if( explorerPath ) {
    fsys.delete(io.appData("iconcache.db"));
    process.execute(explorerPath);

    ::Shell32.SHChangeNotify(0x8000000/*_SHCNE_ASSOCCHANGED*/,0,0,0);

    //鍒锋柊鏂囦欢灞炴�?    //::Shell32.SHChangeNotifyW(0x800/*_SHCNE_ATTRIBUTES*/,5/*_SHCNF_srcPath*/,string.toUtf16("鏂囦欢璺緞"),0);
}

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Desktop/Restart-Explorer.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Desktop/Restart-Explorer.md')

