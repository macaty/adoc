[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 批处理代码支持用 aardio 模板语法嵌入 aardio 代码

```aardio aardio
//aardio 调用批处理入�?import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="批处理代码支持用 aardio 模板语法嵌入 aardio 代码";right=875;bottom=625)
winform.add(
editBat={cls="edit";left=27;top=14;right=848;bottom=312;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=1};
editResult={cls="edit";left=26;top=392;right=848;bottom=569;db=1;dl=1;dr=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=2};
plus={cls="plus";text="执行批处�?;left=606;top=326;right=778;bottom=371;align="left";bgcolor=-5197169;db=1;dr=1;font=LOGFONT(h=-16);iconStyle={align="left";font=LOGFONT(h=-16;name='FontAwesome');padding={left=20}};iconText='\uF17A';notify=1;textPadding={left=42};z=3}
)
/*}}*/

//批处理混合编程指�?https://www.aardio.com/zh-cn/doc/library-guide/std/process/batch.html
import process.batch;
winform.plus.oncommand = function(id,event){

    //优先调用 64 位命令或有些命令只有 64 位请改为 process.batch.wow64
    var prcs = process.batch(winform.editBat.text/*批处理文件或代码*/,{
        exepath = io._exepath; //传命名参数给批处理内�?aardio 代码，使�?owner.exepath 接收
        "批处理启动参�?"; //批处理使�?%1 接收第一个参�?        "批处理启动参�?"; //批处理使�?%2 接收第一个参�?    })

    winform.plus.disabledText = {'\uF254';'\uF251';'\uF252';'\uF253';'\uF250';text=''}

    //out 用于接收批处理的全部输出(包含错误输出), err 为错误信息（无错误为 null �?    var out,err = prcs.readAll(); //可在参数 @1 中指定匹配模式查找指定字符串
    //prcs.close();//上面的函数已经自动调用了 close 函数

    winform.editResult.print(out);
    winform.plus.disabledText = null;
}

//支持模板语法�?https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.html
winform.editBat.text = /*
@echo off
for %%i in (<?

//这里可以嵌入 aardio 代码，使�?print 函数动态生成批处理代码
import fsys;
fsys.enum( "/", "*.*",
    function(dir,filename,fullpath,findData){
        if(filename){
               print(filename," ")
        }
        else {

        }
    },false
);

?>) do echo %%i

echo <?= time() ?>
echo <?= owner.exepath ?>

echo 此批处理接收到的第一个参数："%1"
echo 此批处理接收到的第二个参数："%2"

rem 批处理延�?ping 127.0.0.1 -n 3 >nul

rem 下面自定义批处理进程退出代�?exit /B 123
*/

winform.plus.skin({
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

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Bat/batch.md)

