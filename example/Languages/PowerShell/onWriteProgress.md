[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 PowerShell 之进度条

```aardio aardio
//aardio 调用 PowerShell 之进度条
import win.ui;
/*DSG{{*/
var winform = win.form(text="PowerShell 进度�?;right=606;bottom=463;max=false)
winform.add(
button={cls="button";text="启动 PowerShell 进度�?;left=28;top=385;right=194;bottom=438;z=2};
edit={cls="edit";left=28;top=28;right=575;bottom=314;autohscroll=false;edge=1;multiline=1;vscroll=1;z=3};
plus={cls="plus";left=29;top=327;right=575;bottom=361;align="left";bgcolor=6447459;font=LOGFONT(h=-16);forecolor=9959653;hide=1;notify=1;textPadding={left=25};z=1}
)
/*}}*/

//设置进度区间，可自动切换到进度条显示模式
winform.plus.setProgressRange(1,100);

//io.open() //打开控制台查看线程错误信�?winform.button.oncommand = function(id,event){
    winform.plus.hide = false;
    winform.button.disabledText = {"�?;"�?;"�?;"�?;"�?;"�?};

    thread.invoke(
        function(winform){

            import dotNet.ps;

            dotNet.ps.onWrite = function(str){
                //PowerShell 新版@str以换行结束，旧版无换行且会追加一个空字符串，winform.edit.print() 仅在需要时自动补换行�?                if(#str) winform.edit.print(string.trimright(str));
            }

            dotNet.ps.onWriteProgress = function(sourceId,record){
                //PowerShell 回调出错不会抛出异常，如果有需要在函数内部自行 try catch 捕获代码错误
                winform.plus.text = record.StatusDescription;
                winform.plus.progressPercentage = record.PercentComplete;
            }

            dotNet.ps(`
1..100 | ForEach-Object {
Write-Progress -Activity 'Counting' -Status "Processing $_" -PercentComplete $_
Write-Output "Processing $_ ``r``n"
Start-Sleep -Milliseconds (55-$_/2)
            }`);

            winform.button.disabledText = null;
            winform.plus.hide = true;
            winform.plus.progressPercentage = 0;
        },winform
    )

}

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/PowerShell/onWriteProgress.md)

