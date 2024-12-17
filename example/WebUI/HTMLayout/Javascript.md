[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: HTMLayout 宓屽叆鑴氭湰

```aardio aardio
//宓屽叆鑴氭湰
import win.ui;
/*DSG{{*/
var winform = ..win.form(text="HTMLayout 宓屽叆鑴氭湰";right=599;bottom=399;)
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
        ele.innerText = "Javascript鎵ц缁撴灉:娴嬭瘯涓�涓?
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

//娣诲姞榛樿CSS
wbLayout.appendMasterCss( "
    script[type='text/javascript']{ behavior:javascript; }
    script[type='text/aardio'] { behavior:aardio; }
")
wbLayout.write(html)

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/Javascript.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/Javascript.md')

