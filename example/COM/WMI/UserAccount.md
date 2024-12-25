[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: RUNAS//系统账号管理

```aardio aardio
//RUNAS//WMI - 系统账号管理
import win.ui;
/*DSG{{*/
var winform = win.form(text="账号管理";right=602;bottom=379;max=false;)
winform.add(
btnDisablePasswordExpires={cls="button";text="设为密码永不过期";left=241;top=322;right=387;bottom=361;z=3};
btnEnablePasswordExpires={cls="button";text="取消密码永不过期";left=414;top=322;right=560;bottom=361;z=4};
btnOpenSetting={cls="button";text="打开系统账号设置";left=38;top=322;right=184;bottom=361;z=2};
listview={cls="listview";left=22;top=20;right=580;bottom=308;acceptfiles=1;bgcolor=16777215;dl=1;dr=1;edge=1;font=LOGFONT(name='SimSun');fullRow=1;gridLines=1;msel=false;z=1}
)
/*}}*/

winform.listview.insertColumn("用户�?,150 )
winform.listview.insertColumn("密码永不过期",-1 )

import com.wmi;
var reload = function(){

    var index = 0;
    for item in com.wmi.eachProperties("SELECT * FROM Win32_UserAccount WHERE Status=@status"
            ,{status="OK"}) {

        index++;

        if(index>winform.listview.count){
            winform.listview.addItem({
                item.Name,
                !item.PasswordExpires
            })
        }
        else {
            //原地修改，避免闪�?            winform.listview.setItemText({
                item.Name,
                !item.PasswordExpires
            },index)
        }
    }

    for(i=winform.listview.count;index+1;-1){
        winform.listview.delItem(i)
    }
}

import process.control;
winform.btnOpenSetting.oncommand = function(id,event){
    process.control("userpasswords2");
}

setPasswordExpires = function(enabled){
    var selIndex = winform.listview.selIndex;
    if(!selIndex) return winform.msgboxErr("请选定要设置的用户!")

    var name  = winform.listview.getItemText(selIndex,1)
    var user  = com.wmi.get("SELECT * FROM Win32_UserAccount WHERE Name=@name"
            ,{status="OK",name=name})

    if(!user){
        return winform.msgboxErr("查询用户失败!")
    }

    user.PasswordExpires = enabled;
    user.Put_();
    reload();
}

winform.btnDisablePasswordExpires.oncommand = function(id,event){
    setPasswordExpires(false);
}

winform.btnEnablePasswordExpires.oncommand = function(id,event){
    setPasswordExpires(true);
}

reload();

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/COM/WMI/UserAccount.md)

