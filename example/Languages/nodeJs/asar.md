[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 通过 Node.js 调用 asar �?
```aardio aardio
//aardio 通过 Node.js 调用 asar �?import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio做界面调用node.js解压asar文件";right=714;bottom=199)
winform.add(
btnExtractAll={cls="button";text="解包";left=423;top=113;right=587;bottom=155;z=3};
btnOpen={cls="button";text="选择要解包的文件";left=499;top=42;right=657;bottom=85;z=2};
button={cls="button";text="用纯 aardio  代码打包或解�?;left=132;top=112;right=409;bottom=154;z=4};
editAsarFile={cls="edit";left=55;top=45;right=494;bottom=83;edge=1;multiline=1;z=1}
)
/*}}*/

import fsys.dlg;
winform.btnOpen.oncommand = function(id,event){
    winform.editAsarFile.text = fsys.dlg.open("*.asar|*.asar|","选择asar文件",,winform.hwnd)
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

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/nodeJs/asar.md)

