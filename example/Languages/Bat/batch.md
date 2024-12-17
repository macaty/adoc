[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鎵瑰鐞嗕唬鐮佹敮鎸佺敤 aardio 妯℃澘璇硶宓屽叆 aardio 浠ｇ爜

```aardio aardio
//aardio 璋冪敤鎵瑰鐞嗗叆闂?import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="鎵瑰鐞嗕唬鐮佹敮鎸佺敤 aardio 妯℃澘璇硶宓屽叆 aardio 浠ｇ爜";right=875;bottom=625)
winform.add(
editBat={cls="edit";left=27;top=14;right=848;bottom=312;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=1};
editResult={cls="edit";left=26;top=392;right=848;bottom=569;db=1;dl=1;dr=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=2};
plus={cls="plus";text="鎵ц鎵瑰鐞?;left=606;top=326;right=778;bottom=371;align="left";bgcolor=-5197169;db=1;dr=1;font=LOGFONT(h=-16);iconStyle={align="left";font=LOGFONT(h=-16;name='FontAwesome');padding={left=20}};iconText='\uF17A';notify=1;textPadding={left=42};z=3}
)
/*}}*/

//鎵瑰鐞嗘贩鍚堢紪绋嬫寚鍗?https://www.aardio.com/zh-cn/doc/library-guide/std/process/batch.html
import process.batch;
winform.plus.oncommand = function(id,event){

    //浼樺厛璋冪敤 64 浣嶅懡浠ゆ垨鏈変簺鍛戒护鍙湁 64 浣嶈鏀逛负 process.batch.wow64
    var prcs = process.batch(winform.editBat.text/*鎵瑰鐞嗘枃浠舵垨浠ｇ爜*/,{
        exepath = io._exepath; //浼犲懡鍚嶅弬鏁扮粰鎵瑰鐞嗗唴鐨?aardio 浠ｇ爜锛屼娇鐢?owner.exepath 鎺ユ敹
        "鎵瑰鐞嗗惎鍔ㄥ弬鏁?"; //鎵瑰鐞嗕娇鐢?%1 鎺ユ敹绗竴涓弬鏁?        "鎵瑰鐞嗗惎鍔ㄥ弬鏁?"; //鎵瑰鐞嗕娇鐢?%2 鎺ユ敹绗竴涓弬鏁?    })

    winform.plus.disabledText = {'\uF254';'\uF251';'\uF252';'\uF253';'\uF250';text=''}

    //out 鐢ㄤ簬鎺ユ敹鎵瑰鐞嗙殑鍏ㄩ儴杈撳嚭(鍖呭惈閿欒杈撳嚭), err 涓洪敊璇俊鎭紙鏃犻敊璇负 null 锛?    var out,err = prcs.readAll(); //鍙湪鍙傛暟 @1 涓寚瀹氬尮閰嶆ā寮忔煡鎵炬寚瀹氬瓧绗︿覆
    //prcs.close();//涓婇潰鐨勫嚱鏁板凡缁忚嚜鍔ㄨ皟鐢ㄤ簡 close 鍑芥暟

    winform.editResult.print(out);
    winform.plus.disabledText = null;
}

//鏀寔妯℃澘璇硶锛?https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.html
winform.editBat.text = /*
@echo off
for %%i in (<?

//杩欓噷鍙互宓屽叆 aardio 浠ｇ爜锛屼娇鐢?print 鍑芥暟鍔ㄦ�佺敓鎴愭壒澶勭悊浠ｇ爜
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

echo 姝ゆ壒澶勭悊鎺ユ敹鍒扮殑绗竴涓弬鏁帮細"%1"
echo 姝ゆ壒澶勭悊鎺ユ敹鍒扮殑绗簩涓弬鏁帮細"%2"

rem 鎵瑰鐞嗗欢鏃?ping 127.0.0.1 -n 3 >nul

rem 涓嬮潰鑷畾涔夋壒澶勭悊杩涚▼閫�鍑轰唬鐮?exit /B 123
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Bat/batch.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Bat/batch.md')

