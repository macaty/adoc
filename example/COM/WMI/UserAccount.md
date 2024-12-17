[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: RUNAS//绯荤粺璐﹀彿绠＄悊

```aardio aardio
//RUNAS//WMI - 绯荤粺璐﹀彿绠＄悊
import win.ui;
/*DSG{{*/
var winform = win.form(text="璐﹀彿绠＄悊";right=602;bottom=379;max=false;)
winform.add(
btnDisablePasswordExpires={cls="button";text="璁句负瀵嗙爜姘镐笉杩囨湡";left=241;top=322;right=387;bottom=361;z=3};
btnEnablePasswordExpires={cls="button";text="鍙栨秷瀵嗙爜姘镐笉杩囨湡";left=414;top=322;right=560;bottom=361;z=4};
btnOpenSetting={cls="button";text="鎵撳紑绯荤粺璐﹀彿璁剧疆";left=38;top=322;right=184;bottom=361;z=2};
listview={cls="listview";left=22;top=20;right=580;bottom=308;acceptfiles=1;bgcolor=16777215;dl=1;dr=1;edge=1;font=LOGFONT(name='SimSun');fullRow=1;gridLines=1;msel=false;z=1}
)
/*}}*/

winform.listview.insertColumn("鐢ㄦ埛鍚?,150 )
winform.listview.insertColumn("瀵嗙爜姘镐笉杩囨湡",-1 )

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
            //鍘熷湴淇敼锛岄伩鍏嶉棯鐑?            winform.listview.setItemText({
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
    if(!selIndex) return winform.msgboxErr("璇烽�夊畾瑕佽缃殑鐢ㄦ埛!")

    var name  = winform.listview.getItemText(selIndex,1)
    var user  = com.wmi.get("SELECT * FROM Win32_UserAccount WHERE Name=@name"
            ,{status="OK",name=name})

    if(!user){
        return winform.msgboxErr("鏌ヨ鐢ㄦ埛澶辫触!")
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/WMI/UserAccount.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/WMI/UserAccount.md')

