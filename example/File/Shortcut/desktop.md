[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 妗岄潰鍥炬爣

```aardio aardio
//妗岄潰鍥炬爣

import fsys.lnk;

var lnk = fsys.lnk();
lnk.description = "杩欐槸涓�涓揩鎹锋柟寮?

lnk.path = io._exepath //璁剧疆鐩爣璺緞

//璁剧疆鍥炬爣锛屽鏋滃弬鏁癅1 涓?EXE 璺緞锛屽弬鏁?@2 鎸囧畾鍥炬爣绱㈠紩锛? 涓洪粯璁ゅ浘鏍?lnk.setIcon(io._exepath,0);

lnk.save(
    io.getSpecial(0x0010 /*_CSIDL_DESKTOPDIRECTORY*/,"鎴戠殑蹇嵎鏂瑰紡.lnk" )
)

import com;
com.CreateObject("Shell.Application").MinimizeAll();

//鍒锋柊妗岄潰鍥炬爣
::Shell32.SHChangeNotify(0x8000000/*_SHCNE_ASSOCCHANGED*/,0,0,0);

//鍒锋柊鏂囦欢灞炴�?//::Shell32.SHChangeNotify(0x800/*_SHCNE_ATTRIBUTES*/,1/*_SHCNF_srcPath*/,"鏂囦欢璺緞",0);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/Shortcut/desktop.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/Shortcut/desktop.md')

