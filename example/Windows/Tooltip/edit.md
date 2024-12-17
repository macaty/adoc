[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鏂囨湰妗嗘彁绀?
```aardio aardio
//鏂囨湰妗嗘彁绀?import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=469)
winform.add(
btnError={cls="button";text="閿欒";left=280;top=306;right=390;bottom=353;z=2};
btnInfo={cls="button";text="鎻愮ず";left=539;top=306;right=649;bottom=353;z=4};
btnWarning={cls="button";text="璀﹀憡";left=410;top=306;right=520;bottom=353;z=3};
edit={cls="edit";text="Edit";left=129;top=179;right=394;bottom=218;edge=1;multiline=1;z=1}
)
/*}}*/

winform.btnError.oncommand = function(id,event){
    winform.edit.showErrorTip("杩欐槸鏍囬","杩欐槸瑕佹樉绀虹殑閿欒淇℃伅")
}

winform.btnWarning.oncommand = function(id,event){
    winform.edit.showWarningTip("杩欐槸鏍囬","杩欐槸瑕佹樉绀虹殑閿欒淇℃伅")
}

winform.btnInfo.oncommand = function(id,event){
    winform.edit.showInfoTip("杩欐槸鏍囬","杩欐槸瑕佹樉绀虹殑閿欒淇℃伅",true)
}

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Tooltip/edit.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Tooltip/edit.md')

