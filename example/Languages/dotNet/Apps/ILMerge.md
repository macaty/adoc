[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 合并 .NET 程序集工具源�?
```aardio aardio
//合并 .NET 程序集工具源�?//请改�?dotNet.reference
import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text=".Net 程序集合并工�?;right=774;bottom=508)
winform.add(
btnIFileOpenDir={cls="plus";left=495;top=13;right=539;bottom=43;align="left";color=3947580;dr=1;dt=1;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=8}};iconText='\uF07C';notify=1;textPadding={left=25};z=11};
btnMerge={cls="plus";text="合并程序�?;left=421;top=390;right=550;bottom=420;align="left";bgcolor=-5197169;db=1;dr=1;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=20}};iconText='\uF0F2';notify=1;textPadding={left=39};z=12};
btnOpenInputFiles={cls="plus";left=704;top=56;right=741;bottom=86;align="left";color=3947580;dr=1;dt=1;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=8}};iconText='\uF0C5';notify=1;textPadding={left=25};z=13};
btnOpenOutputPath={cls="plus";left=359;top=143;right=396;bottom=173;align="left";color=3947580;dr=1;dt=1;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=8}};iconText='\uF064';notify=1;textPadding={left=25};z=14};
chkDebug={cls="checkbox";text="调试版本";left=266;top=188;right=427;bottom=214;dl=1;dr=1;dt=1;z=4};
cmbTargetPlatform={cls="combobox";left=133;top=185;right=235;bottom=207;dl=1;dt=1;edge=1;items={"v4";"v2"};mode="dropdownlist";z=2};
editInput={cls="edit";text="*.dll";left=134;top=57;right=691;bottom=126;autohscroll=false;dl=1;dr=1;dt=1;edge=1;multiline=1;vscroll=1;z=7};
editLog={cls="edit";left=134;top=229;right=691;bottom=381;autohscroll=false;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;vscroll=1;z=1};
editOutput={cls="edit";text="output.dll";left=133;top=143;right=347;bottom=168;dl=1;dr=1;dt=1;edge=1;z=5};
editWorkDir={cls="edit";left=134;top=15;right=482;bottom=40;dl=1;dr=1;dt=1;edge=1;z=10};
lbOutput={cls="static";text="输出文件名：";left=36;top=146;right=124;bottom=165;align="right";dl=1;dt=1;transparent=1;z=6};
static={cls="static";text="目标 .Net 版本�?;left=16;top=184;right=124;bottom=203;align="right";dl=1;dt=1;transparent=1;z=3};
static2={cls="static";text="输入程序集：";left=36;top=61;right=124;bottom=80;align="right";dl=1;dt=1;transparent=1;z=8};
static3={cls="static";text="工作目录�?;left=31;top=19;right=124;bottom=38;align="right";dl=1;dt=1;transparent=1;z=9};
static4={cls="static";text="如果需要在运行时加载单个原始程序集，则合并后的新程序集可能会出错�?这时可以改用 dotNet.reference() 函数注册多个内存程序集到『虚拟程序集引用表』，
aardio �?.NET 程序集本身都支持这种『虚拟程序集』（除非存在访问本地程序集文件的代码）�?但如果程序中用到相互不兼容但名字相同的程序集，用 ILMerge 合并程序集也许能解决问题�?;left=133;top=431;right=735;bottom=503;notify=1;transparent=1;z=15}
)
/*}}*/

import fsys;
import dotNet.merge;
winform.btnMerge.oncommand = function(id,event){
    if(!fsys.isDir(winform.editWorkDir.text)){
        winform.editWorkDir.showErrorTip("请指定有效的工作目录");
        return;
    }
    winform.btnMerge.disabledText = {'\uF254';'\uF251';'\uF252';'\uF253';'\uF250';text=''}

    var ilMerge = dotNet.merge(winform.editWorkDir.text);
    ilMerge.debug = winform.chkDebug.checked;
    ilMerge.targetPlatform = winform.cmbTargetPlatform.selText;
    ilMerge.log = true;

    var prcs = ilMerge.popen(winform.editOutput.text,string.splitEx(winform.editInput.text,"[,\r\n]"));
    prcs.logResponse(winform.editLog);
    prcs.waitOne();

    winform.btnMerge.disabledText = null;
}

import fsys;
import fsys.dlg;
winform.btnOpenInputFiles.oncommand = function(id,event){
    var paths = fsys.dlg.openEx("*.dll|*.dll||","选择要合并的程序�?,winform.editWorkDir.text)
    if(#paths){
        if(!#winform.editWorkDir.text){
            winform.editWorkDir.text = io.splitpath(paths[1]).dir;
        }

        var items = {}
        for(k,v in paths){
            table.push(items,..fsys.path.relative(v,winform.editWorkDir.text,false):v);
        }

        winform.editInput.text = string.join(items,",");
    }
}

import fsys.dlg.dir;
winform.btnIFileOpenDir.oncommand = function(id,event){
    var path = fsys.dlg.dir(,winform,'请选择目录')
    if(path){
        winform.editWorkDir.text = path;
    }
}

import process;
winform.btnOpenOutputPath.oncommand = function(id,event){
    if(!fsys.isDir(winform.editWorkDir.text)){
        winform.editWorkDir.showErrorTip("请先指定有效的工作目�?);
        return;
    }

    if(!#winform.editOutput.text){
        winform.editOutput.showErrorTip("请先指定有效的输出文件名");
        return;
    }

    var path = fsys.path.full(winform.editOutput.text,winform.editWorkDir.text);
    if(!io.exist(path)){
        winform.editOutput.showWarningTip("尚未生成输出文件,请点击下面的「合并程序集�?);
        return;
    }
    process.exploreSelect(path);

}

var style = {
    transButton = {
        color={
            active=0xFF00FF00;
            default=0xFF3C3C3C;
            disabled=0xFF6D6D6D;
            hover=0xFFFF0000
        }
    };
    button = {
        background={
            default=0x668FB2B0;
            disabled=0xFFCCCCCC;
            hover=0xFF928BB3
        };
        color={
            default=0xFF000000;
            disabled=0xFF6D6D6D
        }
    }
}

winform.btnOpenOutputPath.skin(style.transButton);
winform.btnOpenInputFiles.skin(style.transButton);
winform.btnIFileOpenDir.skin(style.transButton);
winform.btnMerge.skin(style.button);

winform.cmbTargetPlatform.selIndex = 1;
winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Apps/ILMerge.md)

