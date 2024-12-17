[aardio 鏂囨。](../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 绐楀彛绋嬪簭 - 鍏ラ棬

```aardio aardio
//绐楀彛绋嬪簭 - 鍏ラ棬
//璇锋寜 F5 杩愯鏌ョ湅鏁欑▼

/*
绐楀彛绋嬪簭鍏ラ棬鎸囧崡锛?https://www.aardio.com/zh-cn/doc/library-guide/std/win/ui/basic.html

鍒涘缓绐楀彛涓庢帶浠跺叆闂ㄦ暀绋嬶細
https://www.aardio.com/zh-cn/doc/library-guide/std/win/ui/create-winform.html
*/

var fb = fiber.create(
    function(){
        import win.ui;
        mainForm = win.form(text="绐楀彛绋嬪簭鍏ラ棬";right=959;bottom=591)

        mainForm.add(
        custom={cls="\dlg\main\userInfo.aardio";text="custom";left=568;top=944;right=944;bottom=584;db=1;dr=1;z=1};
        tab={cls="tab";left=8;top=16;right=944;bottom=536;db=1;dl=1;dr=1;dt=1;edge=1;z=2}
        )

        mainForm.tab.loadForm("\dlg\main\tabs1.aardio");
        mainForm.tab.loadForm("\dlg\main\tabs2.aardio");
        mainForm.tab.loadForm("\dlg\main\tabs3.aardio");

        mainForm.show();
        win.loopMessage();

    },"~\extensions\wizard\project2\template\winform\"
)

fiber.resume(fb)

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/QuickStart.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/QuickStart.md')

