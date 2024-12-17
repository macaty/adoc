[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: COM 接口 - shell 外壳

```aardio aardio
//COM 接口 - shell 外壳
//外壳指的是操作系统与用户交互的界面，主要指资源管理器、桌面等�?
import com.shell;
import process;
import sys.networkIsolation;
import console;

var shell = com.shell();//等价�?shell = com.CreateObject("Shell.Application");
/*
shell.CascadeWindows() //层叠窗口
shell.TileHorizontally(); //横向平铺窗口
shell.TileVertically(); //纵向平铺窗口
shell.MinimizeAll(); //最小化所有窗�?shell.UndoMinimizeALL(); //撤消全部最小化
*/

//获取目录对象
var folder = shell.Namespace( io.fullpath("~/config"));

//获取文件对象
var file = folder.ParseName("SYS.CFG");

/*
调用菜单命令�?菜单命令并不完全等价于菜单显示文本，而且与语言无关�?所以在中文系统上不需要改为中文字符串�?*/
file.InvokeVerb("Copy");

if( _WIN10_LATER ){
    for i,item in com.shell.eachApp(){
        console.log( item.name, item.path );
    }

    //获取所有应用容�?参考范例："~/example/Windows/ListView/uwpExemption.aardio"
    var containers = sys.networkIsolation.getAppContainers()

    com.shell.activateApp('Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge'
        , 'https://www.aardio.com');

    // 下面这样也可以打开WIN10应用
    // process.explore("shell:appsFolder\Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge")

    //打开应用商店，且修复 ms-windows-store:// 协议
    com.shell.activateApp("Microsoft.WindowsStore_8wekyb3d8bbwe!App");

    /*
    有时候系统出现问�?ms-windows-store 协议可能用不了，下面的方法就打不开�?    �?com.shell.activateApp("Microsoft.WindowsStore_8wekyb3d8bbwe!App") 可以打开�?    而且打开一次，ms-windows-store 协议就正常了�?    */
    //process.execute("ms-windows-store://home")
}

/***********************
实际�?shell32.dll 也提供很多与外壳操作有关�?API 函数�?aardio 已默认加载了 shell32.dll 并创建了 ::Shell32 对象�?
例如调用 SHChangeNotify 刷新�?::Shell32.SHChangeNotify(0x8000000/*_SHCNE_ASSOCCHANGED*/,0,0,0);

更多函数参考：
https://learn.microsoft.com/zh-cn/windows/win32/api/shlobj_core
***********************/

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/Others/Shell.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/Others/Shell.md')

