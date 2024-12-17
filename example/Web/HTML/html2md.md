[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: HTML 杞?Markdown

````aardio aardio
//HTML 杞?Markdown
import console.int;
import web.turndown;

var turndownService = web.turndown( codeBlockStyle = "fenced" );
turndownService.remove('script');
turndownService.remove('style');

//鍚敤 gfm锛圙itHub Flavored Markdown锛夋彃浠躲�?turndownService.useGfm()

// 娣诲姞鑷畾涔夎鍒欏鐞嗗甫绫诲悕鐨勪唬鐮佸潡
turndownService.addRule('codeBlock', "{
    filter: function(node) {
        return node.nodeName === 'PRE' && node.classList.contains('code');
    },
    replacement: function(content, node) {
        var language = node.classList.item(1)  || '';
        language = language.replace(/^language-/, '');
        return '```' + language + '\n' + content.trim() + '\n```';
    }
}");

var html = /****
 <pre class="code aardio"><code>
 //杩欓噷闈㈠緢澶氫唬鐮? //杩欓噷闈㈠緢澶氫唬鐮? </code></pre>
****/

//鐢ㄦ硶鍙傝�? https://github.com/mixmark-io/turndown
var md = turndownService.turndown(
    html
);

console.log(md);

//Markdown 杞崲涓?HTML
//import string.gfmark;
//var html = string.gfmark.render(md);
//console.log(html);

````

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/HTML/html2md.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/HTML/html2md.md')

