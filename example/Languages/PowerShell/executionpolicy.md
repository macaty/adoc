[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: PowerShell 脚本文件执行权限设置工具

```aardio aardio
//aardio 设置 ps1 权限工具
import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="PowerShell 脚本文件执行权限设置工具";right=759;bottom=469;bgcolor=16777215;max=false)
winform.add(
btnOpenPs1={cls="plus";text='\uF07C';left=678;top=333;right=713;bottom=368;color=3947580;db=1;dr=1;font=LOGFONT(h=-15;name='FontAwesome');notify=1;z=5};
btnOpenPsIse={cls="button";text="启动 PowerShell ISE ";left=314;top=386;right=687;bottom=445;bgcolor=16777215;color=14120960;db=1;dl=1;dr=1;font=LOGFONT(h=-14);note="可选在上面指定工作目录或�?*.ps1 脚本文件路径";z=2};
chkExecutionPolicy={cls="plus";text="已禁止执�?PowerShell 脚本文件";left=73;top=41;right=621;bottom=82;align="left";color=255;dl=1;dr=1;dt=1;font=LOGFONT(h=-19);iconStyle={align="left";font=LOGFONT(h=-27;name='FontAwesome');padding={left=9}};iconText='\uF204';notify=1;textPadding={left=49};z=1};
edit={cls="edit";left=81;top=104;right=712;bottom=282;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;z=3};
editPs1Path={cls="plus";left=81;top=336;right=674;bottom=362;align="right";border={bottom=1;color=-6908266};db=1;dl=1;dr=1;editable=1;font=LOGFONT(h=-13);textPadding={top=6;bottom=2};z=4}
)
/*}}*/

winform.chkExecutionPolicy.skin({
    text = "已禁止执�?PowerShell 脚本文件";
    iconText='\uF204';
    color = {
        default = 0xFFFF0000;
    };

    checked = {
        text="已允�?PowerShell 脚本文件";
        iconText='\uF205';
        color = {
            default = 0xFF008000;
        };
    }
});

import process.popen;
import process.admin;
winform.chkExecutionPolicy.oncommand = function(id,event){

    var ps = process.popen.ps("Set-ExecutionPolicy","-Confirm:$False","-Force"
        ,"-Scope",process.admin.isRunAs()?"LocalMachine":"CurrentUser"
        ,"-ExecutionPolicy",winform.chkExecutionPolicy.checked?"RemoteSigned":"Restricted")

    if(ps){
        winform.edit.print(ps.readAll());
        ps.close();
    }
}

var psPolicy = process.popen.ps("Get-ExecutionPolicy","-Scope",process.admin.isRunAs()?"LocalMachine":"CurrentUser")
if(psPolicy){
    winform.chkExecutionPolicy.checked = !! psPolicy.readAll("<RemoteSigned>|<Bypass>|<Unrestricted>");
    psPolicy.close()
}

winform.btnOpenPs1.skin(
    color = {
        active=0xFF00FF00;
        default=0xFF3C3C3C;
        disabled=0xFF9D9D9D;
        hover=0xFFFF0000
    }
)

import fsys.dlg;
winform.btnOpenPs1.oncommand = function(id,event){
    var path = fsys.dlg.open("*.ps1|*.ps1||",'请选择要打开�?ps1 文件')
    if(path){
        winform.editPs1Path.text = path;
    }
}

winform.editPs1Path.setCueBannerText('请输�?*.ps1 脚本文件路径')

import process.wow64;
winform.btnOpenPsIse.oncommand = function(id,event){
    var path = io.fullpath(winform.editPs1Path.text);
    if(!(io.exist(path) && string.endWith(path,".ps1",true))){
        return winform.editPs1Path.editBox.showErrorTip("请指定正确的 *.ps1 脚本文件路径");
    }

    process.wow64.execute("powershell_ise.exe",`-File "`+io.fullpath(winform.editPs1Path.text)+`"`,,,io.splitpath(winform.editPs1Path.text).dir)
}

winform.onDropFiles = function(files){
    winform.editPs1Path.text = files[1];
}

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/PowerShell/executionpolicy.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/PowerShell/executionpolicy.md')

