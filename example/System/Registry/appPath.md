[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 注册表操�?- 添加系统搜索路径

```aardio aardio
//注册表操�?- 添加系统搜索路径
import win.ui;
import win.dlg.message;
/*DSG{{*/
var winform = win.form(text="添加到系统搜索路�?;right=640;bottom=225;max=false)
winform.add(
btnAdd={cls="button";text="添加到系统搜索路�?;left=25;top=114;right=474;bottom=181;color=14120960;font=LOGFONT(h=-14);note="添加后可�?Win + S 输入名字或在资源管理器地址栏直接输入名字打开";z=1};
cmbPath={cls="combobox";left=60;top=49;right=581;bottom=73;edge=1;items={};mode="dropdown";z=2};
static={cls="static";text="可输�?EXE 名搜索运行过的程序路径：";left=60;top=26;right=485;bottom=45;color=6974058;transparent=1;z=3}
)
/*}}*/

import win.debounce;
import process.cache;
winform.cmbPath.onEditChange  = win.debounce(function(){
    var filename = winform.cmbPath.text;
    filename = string.trim(filename,` "`);

    if(io.exist(filename)) return;

    var lst = process.cache.list(false);
    var files = table.filter(lst,function(v,index){
        var f = io.splitpath(v).file;
        return(f &&..string.startWith(f,filename,true));
    })

    winform.cmbPath.autoComplete(files:{},1) //更新下拉列表
},300)

import sys.reg;
winform.btnAdd.oncommand = function(id,event){
    if(!io.exist(winform.cmbPath.text)){
        return winform.cmbPath.editBox.showErrorTip("请指定有效程序路�?);
    }

    /*
    不用复制文件到系统目录，不用改环境变量，不需要管理权限�?    简单的改一下注册表，就可实现按 Win + S 输入名字或在资源管理器地址栏直接输入名字打开程序
    */
    var tPath = io.splitpath(winform.cmbPath.text);
    sys.reg.setValue("",winform.cmbPath.text,`SOFTWARE\Microsoft\Windows\CurrentVersion\App Paths\` + tPath.file);

    winform.msgGreat("已添加到系统搜索路径");
}

winform.cmbPath.editBox.modifyStyle(,2/*_ES_RIGHT*/);//右对�?
//拖动文件到窗�?winform.onDropFiles = function(files){
    winform.cmbPath.text = files[1];
}

winform.btnAdd.setFocus();

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Registry/appPath.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Registry/appPath.md')

