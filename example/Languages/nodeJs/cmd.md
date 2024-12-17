[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 通过 Node.js 安装并调�?uglifyjs 命令

```aardio aardio
//aardio 通过 Node.js 安装并调�?uglifyjs 命令
import nodeJs;
import console.int;

//打开控制台，回显 Node.js 命令输出
console.open();

//如果未安�?uglify-js 模块则安�?nodeJs.require("uglify-js");

/*
执行 uglify-js 命令�?请参考文�? https://github.com/mishoo/UglifyJS?tab=readme-ov-file#command-line-usage

nodJs.cmd 的第一个参数指这下命令程序文件名�?如果指定三个以上的参数，则用逗号分开多个参数�?�?string.args 自动处理命令行转义，按需添加首尾双引号�?*/
nodeJs.cmd("uglifyjs",
    "js-yaml.js", //输入 js 文件路径，当前目录由 nodeJs.workDir 指定
    "--compress",//压缩
    "--beautify","max_line_len=1000,indent_level=0", //限制单行最大字符数，并且取消缩�?    //"--mangle",
    "--ie",//兼容 web.script,web.form
    "--verbose",
    "--output","your-filename.min.js",
)

/*
nodJs.cmd 如果仅用第二个字符串参数指定命令行参数，
可在一个字符串里用空格分开多个参数。由 string.cmdline 按命令行规则解析该参数�?*/
//nodeJs.cmd("uglifyjs","js-yaml.js --compress --beautify max_line_len=1000,indent_level=0 --ie --verbose --output your-filename.min.js");

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/nodeJs/cmd.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/nodeJs/cmd.md')

