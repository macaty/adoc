[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 反编�?PowerShell �?Cmdlet

```aardio aardio
//aardio 反编�?PowerShell �?Cmdlet
import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="PowerShell Cmdlet 反编译工�?;right=491;bottom=311;bgcolor=16777215;max=false)
winform.add(
btnDecompile={cls="plus";text="反编�?;left=366;top=11;right=479;bottom=41;align="left";bgcolor=-5197169;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=20}};iconText='\uF121';notify=1;textPadding={left=39};z=2};
cmdlets={cls="combobox";left=19;top=14;right=350;bottom=40;edge=1;items={};mode="dropdown";z=4};
edit={cls="edit";left=15;top=72;right=480;bottom=300;autohscroll=false;edge=1;multiline=1;vscroll=1;z=1};
plusTip={cls="plus";left=18;top=47;right=475;bottom=65;align="right";font=LOGFONT(name='FontAwesome');z=3}
)
/*}}*/

winform.onOk = function(){
    if(win.getFocus()!=winform.cmdlets.editBox.hwnd){
        winform.cmdlets.setFocus();
        return ;
    }
    winform.btnDecompile.oncommand();
}

winform.cmdlets.onEditChange = function(){
    if(winform.cmdlets.data){
         var text = winform.cmdlets.text;
         var items = table.filter( winform.cmdlets.data, lambda(v) string.startWith(v,text,true) );
         if(!#items){
            items = table.filter( winform.cmdlets.data, lambda(v) string.find(v,"@@"+text) );
         }
         winform.cmdlets.autoComplete(items,1)
    }
}

winform.btnDecompile.oncommand = function(id,event){
    if(!#winform.cmdlets.text){
        return winform.cmdlets.editBox.showErrorTip("请输�?PowerShell 命名名称");
    }

    winform.btnDecompile.disabledText = {'\uF254';'\uF251';'\uF252';'\uF253';'\uF250';text=''};
    var result = thread.invokeAndWait(
        function(winform){

            import process.popen;
            var prcs  = process.popen.ps(`(Get-Command `+winform.cmdlets.text+`).Dll`);
            if(!prcs) return;

            var result = prcs.read(-1);
            if(#result){
                result = string.trim(result);
                winform.edit.text = result;

                if(..string.endWith(result,".dll",true) && io.exist(result)){
                    import dotNet.ilSpy;
                    dotNet.ilSpy(result);
                }
                return result;
            }
        },winform
    )

    if(!#result){
        winform.cmdlets.editBox.showErrorTip("反编�?PowerShell 命令 失败�?);
    }

    winform.btnDecompile.disabledText = null;
}

winform.plusTip.disabledText = {'\uF254';'\uF251';'\uF252';'\uF253';'\uF250';text='正在获取所�?Cmdlet 并准备智能提示数�?}
thread.invoke(
    function(winform){
            import process.popen;
            var prcs  = process.popen.ps(`Get-Command -CommandType Cmdlet`);
            if(!prcs) return;

            var result = prcs.read(-1);
            if(!result) {
                winform.plusTip.disabledText = null;
                winform.edit.top = winform.edit.top - winform.plusTip.height;
                winform.plusTip.close();
                return;
            }

            var i = 0
            var cmdlets = {}
            for( item in string.lines(result,,"\s+") ){

                if(i<3){
                    i++;
                    continue;
                }

                if(#item<3 || item[1][1]=='-'#) continue;
                table.push(cmdlets,item[2]);
            }

            winform.cmdlets.items = cmdlets;
            winform.cmdlets.data = cmdlets;
            winform.plusTip.disabledText = null;
            winform.edit.top = winform.edit.top - winform.plusTip.height;
            winform.plusTip.close();

    },winform
)

winform.btnDecompile.skin({
    background={
        default=0x668FB2B0;
        disabled=0xFFCCCCCC;
        hover=0xFF928BB3
    };
    color={
        default=0xFF000000;
        disabled=0xFF6D6D6D
    }
})

winform.cmdlets.editBox.setCueBannerText("请输�?PowerShell 命令");
winform.cmdlets.editBox.disableInputMethod();

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/PowerShell/decompiler.md)

