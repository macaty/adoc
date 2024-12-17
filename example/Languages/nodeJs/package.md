[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 通过 Node.js 调用 UglifyJS �?
```aardio aardio
//aardio 通过 Node.js 调用 UglifyJS �?import console;
import nodeJs;

//如果未安�?uglify-js 则安�?nodeJs.require("uglify-js");

// 启动 Node.js �?var node = nodeJs.startRpc('global.UglifyJS = require("uglify-js")');

// 压缩选项
var options = {
    ie: true,
    mangle: true,
    output:{
        indent_level: 0,
        max_line_len: 1000,
        beautify: false,
    }
};

// 直接调用 JS 函数，必须是全局对象 global 的成员对象�?var ret = node.UglifyJS.minify({
    "file1.js": "function add(first, second) { return first + second; }",
    "file2.js": "console.log(add(1 + 2, 3 + 4));"
},options);

/*
请参考文�?
https://github.com/mishoo/UglifyJS?tab=readme-ov-file#api-reference
aardio 兼容 JS 表示对象的语法，aardio 参数选项会通过 JSON 传给 Node.js
所�?UglifyJS 文档的代码可以复制到 aardio 里用，基本不需要太多修改�?*/

var ret = node.UglifyJS.minify(
    inet.http.get("https://cdn.jsdelivr.net/npm/js-yaml@3.14.1/dist/js-yaml.js"),
    options )

// 获取 JS 函数返回�?var minJs = ret[["result"]][["code"]];

//复制压缩结果到剪贴板
import win.clip;
win.clip.write(minJs);

console.dump(minJs);
console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/nodeJs/package.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/nodeJs/package.md')

