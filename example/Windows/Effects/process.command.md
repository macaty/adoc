[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 绐楀彛绋嬪簭 - 璺ㄨ繘绋嬭皟鐢ㄥ嚱鏁?
```aardio aardio
//绐楀彛绋嬪簭 - 璺ㄨ繘绋嬭皟鐢ㄥ嚱鏁?import win.ui;
/*DSG{{*/
mainForm = win.form(text="绐楀彛绋嬪簭 - 璺ㄨ繘绋嬭皟鐢ㄥ嚱鏁?;right=581;bottom=373)
mainForm.add(
button={cls="button";text="鍙戦�佽法杩涚▼鍛戒护";left=297;top=309;right=519;bottom=355;z=1};
edit={cls="edit";left=28;top=17;right=555;bottom=298;edge=1;multiline=1;z=2}
)
/*}}*/

import process.command;

//鍔犲叆杩涚▼缇ょ粍,浣跨敤 GUID 鍖哄垎涓嶅悓鐨勮繘绋嬬兢缁?process.command.join("{870819C0-D702-4508-BB0A-5F09E514E23E}")

//娉ㄥ唽杩涚▼鍛戒护瀵硅薄
var processObserver = process.command();
processObserver.testCmd = function(a,b,c){
    mainForm.edit.appendText("testCmd琚皟鐢?鍙傛暟:",a,b,c,'\r\n');
    return 123;
}

//鍙戦�佽繘绋嬪懡浠?mainForm.button.oncommand = function(id,event){
    process.command.testCmd(1,2,",杩涚▼鍛戒护鍙傛暟")

}

mainForm.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Effects/process.command.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Effects/process.command.md')

