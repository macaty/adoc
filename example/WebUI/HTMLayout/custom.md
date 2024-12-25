[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: HTMLayout 自定义控�?
```aardio aardio
//自定义控�?import win.ui;
/*DSG{{*/
var winform = win.form(text="HTMLayout 自定义控�?;right=1014;bottom=523;)
winform.add()
/*}}*/

import web.layout;
var wbLayout = web.layout( winform );

import web.layout.debug;
wbLayout.attachEventHandler( web.layout.debug );

import web.form;
namespace web.layout.behavior.webBrowser {
    onElementControlCreated = function (ltTarget,ltOwner,reason,behaviorParams) {
        var ltCtrl = ltOwner.getCtrl();
        wb = ..web.form( ltCtrl,0x4/*_UIFLAG_NO3DBORDER*/  , , ,true/*securityTrusted*/ )
        ltCtrl.translateAccelerator = function( msg ){
            var message,vk = msg.message,msg.wParam;
            if (   (message == 0x100/*_WM_KEYDOWN*/) || (message== 0x101/*_WM_KEYUP*/) ) {
                if( /**( vk == 0x74/*_VK_F5*/ )
                    || **/( ( vk == 'N'# ) && ( ( ::GetKeyState(0x11/*_VK_CTRL*/) & 0x8000 ) == 0x8000 ) ) )
                {
                    return true;
                }
            }
            return wb._host.tranacc(msg)
        }
        if( !_STUDIO_INVOKED ){
            wb.noScriptErr = true;
        }
        var homepage = ltOwner.getCustomAttribute("homepage");
        if( #homepage ) wb.go(  ltOwner.getCustomAttribute("homepage"))
        ltOwner.sendEvent("onBrowserCreated",1);
    }
    onSize = function (ltOwner) {
        ltOwner.adjustCtrl();
    }
}

//在HTML中引用的控件,需要使用import语句导入aardio
import win.ui.ctrl.static;
import win.ui.ctrl.richedit;
wbLayout.html =/***
<body>

<span style="font:system">
自定义控件很简�?在input,object,widget三种节点中使用cls属性指定控件类名即�?<br />
可选在data-table属性中使用一个table对象指定控件初始化参�?<br />
</span>

<object cls="richedit" data-table="{ text='控件文本';multiline=true }" id="edit" style="font-size:9pt;width:100%; height:50px;"></object>
<widget cls="static" #browser style="width:100%%;height:100%%;"></widget>
widget可以指定相对高度,input,object因为被包含在匿名节点�?无法指定相对高度 <? = " | ",time()," 这里也是可以使用模板语法�? ?>
</body>
***/

wbLayout.css = /**
body{
    margin:20px;
    height:100%%;
    font:system;
}

#browser {
    behavior:web-browser;
    -homepage:"http://www.aardio.com";
}
**/

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/custom.md)

