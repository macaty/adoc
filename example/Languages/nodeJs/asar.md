[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 閫氳繃 Node.js 璋冪敤 asar 鍖?
```aardio aardio
//aardio 閫氳繃 Node.js 璋冪敤 asar 鍖?import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio鍋氱晫闈㈣皟鐢╪ode.js瑙ｅ帇asar鏂囦欢";right=714;bottom=199)
winform.add(
btnExtractAll={cls="button";text="瑙ｅ寘";left=423;top=113;right=587;bottom=155;z=3};
btnOpen={cls="button";text="閫夋嫨瑕佽В鍖呯殑鏂囦欢";left=499;top=42;right=657;bottom=85;z=2};
button={cls="button";text="鐢ㄧ函 aardio  浠ｇ爜鎵撳寘鎴栬В鍖?;left=132;top=112;right=409;bottom=154;z=4};
editAsarFile={cls="edit";left=55;top=45;right=494;bottom=83;edge=1;multiline=1;z=1}
)
/*}}*/

import fsys.dlg;
winform.btnOpen.oncommand = function(id,event){
    winform.editAsarFile.text = fsys.dlg.open("*.asar|*.asar|","閫夋嫨asar鏂囦欢",,winform.hwnd)
}

winform.btnExtractAll.oncommand = function(id,event){
    winform.btnExtractAll.disabled = true;

    thread.invokeAndWait(
        function(winform){
            import nodeJs;

            nodeJs.startEnviron(
                src = winform.editAsarFile.text;
                dest = fsys.getParentDir(winform.editAsarFile.text) ++ fsys.getFileName(winform.editAsarFile.text) + "_ExtractAll";
            )

            nodeJs.require('asar');

            var testjs = /***
            var startEnviron = require('startEnviron')
            var asar = require('asar');

            asar.extractAll(startEnviron.src, startEnviron.dest )
            ***/
            var node = nodeJs.exec(testjs);
        },winform
    )

    winform.btnExtractAll.disabled = false;
}

winform.button.oncommand = function(id,event){
    import ide;
    ide.openDocument("~/example/File/asar/main.aardio")

}

winform.show(true);
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/nodeJs/asar.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/nodeJs/asar.md')

