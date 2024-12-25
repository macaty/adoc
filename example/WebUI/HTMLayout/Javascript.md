[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: HTMLayout 嵌入脚本

```aardio aardio
//嵌入脚本
import win.ui;
/*DSG{{*/
var winform = ..win.form(text="HTMLayout 嵌入脚本";right=599;bottom=399;)
/*}}*/

import web.layout;
var wbLayout = web.layout(winform);

import web.script;
namespace web.layout.behavior{
    namespace javascript{
        var javascript = ..web.script("JavaScript")
        onAttach = function( ltEle ){
            javascript.document = ltEle.root();
            javascript.AddCode( ltEle.innerText );
            return true
        }
    }
    namespace aardio{
        onAttach = function( ltOwner ){
            assert(  loadcode(  ltOwner.innerText ) )( ltOwner.getLayout()  )
            return true
        }
    }
}

html =/***
    <div id="test">......</div>

    <script type='text/javascript'>
        var ele = document.getElementById("test");
        ele.innerText = "Javascript执行结果:测试一�?
    </script>

    <script type='text/aardio'>
        import win;

        var window = ...;
        var $ = function(...){
            return window.querySelectorAll(...);
        }

        var code = $("script[type='text/aardio']")[1].innerText
        win.msgbox( code )
    </script>
***/

//添加默认CSS
wbLayout.appendMasterCss( "
    script[type='text/javascript']{ behavior:javascript; }
    script[type='text/aardio'] { behavior:aardio; }
")
wbLayout.write(html)

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/Javascript.md)

