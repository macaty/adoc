[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: HTML �?Markdown

````aardio aardio
//HTML �?Markdown
import console.int;
import web.turndown;

var turndownService = web.turndown( codeBlockStyle = "fenced" );
turndownService.remove('script');
turndownService.remove('style');

//启用 gfm（GitHub Flavored Markdown）插件�?turndownService.useGfm()

// 添加自定义规则处理带类名的代码块
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
 //这里面很多代�? //这里面很多代�? </code></pre>
****/

//用法参�? https://github.com/mixmark-io/turndown
var md = turndownService.turndown(
    html
);

console.log(md);

//Markdown 转换�?HTML
//import string.gfmark;
//var html = string.gfmark.render(md);
//console.log(html);

````

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/HTML/html2md.md)

