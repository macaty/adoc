[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: Sciter 嵌入原生控件

```aardio aardio
//嵌入原生控件
import win.ui;
/*DSG{{*/
var winform = win.form(text="Sciter 嵌入原生控件";right=1014;bottom=523;)
winform.add()
/*}}*/

import web.sciter;
var sciter = web.sciter( winform );

import web.form;

//�?web.sciter.behavior 名字空间添加自定�?behavior
namespace web.sciter.behavior.webbrowser {

    //节点绑定 behavior 时触发此事件
    onAttach = function (scOwner) {

        //创建控件窗口
        var ltCtrl = scOwner.addCtrl();

        //创建浏览�?        var wb = ..web.form( ltCtrl );

        //屏蔽网页 F5, Ctrl + N 快捷�?        ltCtrl.translateAccelerator = function( msg ){
            var message,vk = msg.message,msg.wParam;
            if (   (message == 0x100/*_WM_KEYDOWN*/) || (message== 0x101/*_WM_KEYUP*/) ) {
                if( ( vk == 0x74/*_VK_F5*/ )
                    || ( ( vk == 'N'# ) && ( ( ::GetKeyState(0x11/*_VK_CTRL*/) & 0x8000 ) ) ) ) {
                    return true;
                }
            }
        }

        if( !_STUDIO_INVOKED ){
            wb.noScriptErr = true;
        }

        var homepage = scOwner.getAttribute("homepage");
        if( #homepage ) wb.go(homepage)

        scOwner.sendEvent("onBrowserCreated",1);
    };

    //节点移除 behavior 时触发此事件
    onDetach = function( scOwner ){
        scOwner.delCtrl();
    };
    //onSize = function (ltOwner) {  ltOwner.adjustCtrl();  }; //custom 控件可以省略
}

import win.ui.ctrl.custom; //在HTML中引用的原生控件，需要先导入 aardio
sciter.html =/***
<body>
    <span style="font:system">
    自定义控件可以象HTMLayout那样,在input,object,widget三种节点中使用cls属性指定控件类名来启用custom这个内建behavior,<br />
    使用此方法时可选在data-table属性中使用一个table对象指定控件初始化参数，示例�?<br /><br />
    </span>

    <span style="font:system">
    在Sciter中也可以新建一个behavior，使用节点提供的 addCtrl函数直接创建自定义控�?    </span>
    <widget  #browser style="width:100%%;height:100%%;" homepage="http://www.aardio.com"></widget>
    widget可以指定相对高度,input,object因为被包含在匿名节点�?无法指定相对高度 <? = " | ",time()," 这里也是可以使用模板语法�? ?>
</body>
***/

sciter.css = /**
body{
    margin:20px;
    height:100%%;
    font:system;
}

#browser {
    behavior: webbrowser;
}
**/

/*
用自定义控件,就不要在 HTML 里写
<html window-frame="extended" window-resizable> 这些代码�?这样拖动会有透明背景出现，可以加�?winform.disableDragFullWindow = true 解决�?*/

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/addCtrl.md)

