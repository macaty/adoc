[aardio 鏂囨。](../../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: translate

```aardio aardio
import win.ui;
import web.form;
/*DSG{{*/
var winform = win.form( bottom=249;scroll=1;right=349;text="aardio form" )
winform.add(  )
/*}}*/

//鍒涘缓web绐椾綋
var wb = web.form( winform );

wb.NewWindow2=function( ppDisp, Cancel) {
    /*寮瑰嚭鏂扮獥鍙ｄ互鍓嶈Е鍙?*/
    winform.setTimeout(
        function(){
            wb.go( wb.translateUrl )
        },1
    )
    return ppDisp, true; /*绗簩涓繑鍥炲�煎鏋滀负鐪?鍒欏彇娑堟柊绐楀彛*/
}

wb.translate = function( url ){
    /*瑙ｆ瀽URL鏃惰Е鍙?*/
    owner.translateUrl = url;
}

//鎵撳紑鐩爣缃戠珯
wb.go("http://www.aardio.com/")
//鏄剧ず绐椾綋
winform.show()
wb.wait("");//绛夊緟鎸囧畾缃戝潃,鍙互浣跨敤妯″紡鍖归厤璇硶

//杩涘叆娑堟伅寰幆
win.loopMessage();
return winform,wb;

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/web.form/Feature/NoPopups/translate.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/web.form/Feature/NoPopups/translate.md')

