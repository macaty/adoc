[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 安装模块

```aardio aardio
//安装模块
import process.python.pip;
//指定 process.python.path = "python.exe" 则调用系统安装的 pip�?
/*
安装模块�?
参数可以用一个字符串指定多个 pip 参数，参数之间以空格分开�?参数用法与原�?pip 一�? https://pip.pypa.io/en/stable/cli/pip_install/

也可以用多个 aardio 参数指定多个 pip 参数，aardio 自动合并所有参数并自动处理转义�?*/
process.python.pip("install jsonrpclib");

//如果指定的模块未安装，则调用 pip 安装
process.python.pip.require("jsonrpclib");

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python AnyVersion/pip.md)

