[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 桌面图标

```aardio aardio
//桌面图标

import fsys.lnk;

var lnk = fsys.lnk();
lnk.description = "这是一个快捷方�?

lnk.path = io._exepath //设置目标路径

//设置图标，如果参数@1 �?EXE 路径，参�?@2 指定图标索引�? 为默认图�?lnk.setIcon(io._exepath,0);

lnk.save(
    io.getSpecial(0x0010 /*_CSIDL_DESKTOPDIRECTORY*/,"我的快捷方式.lnk" )
)

import com;
com.CreateObject("Shell.Application").MinimizeAll();

//刷新桌面图标
::Shell32.SHChangeNotify(0x8000000/*_SHCNE_ASSOCCHANGED*/,0,0,0);

//刷新文件属�?//::Shell32.SHChangeNotify(0x800/*_SHCNE_ATTRIBUTES*/,1/*_SHCNF_srcPath*/,"文件路径",0);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/Shortcut/desktop.md)

