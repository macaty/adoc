[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 创建 curl 进程

```aardio aardio
//创建 curl 进程
import console;

//如果打开控制台，curl.exe 会自动附加到当前控制�?�?console.open();

//默认调用 Win10 1803 及之后系统自带的 curl �?//改为 import process.curl.7.81 可兼容到 XP 系统�?import process.curl;

//创建进程对象，显示控制台窗口与操作进�?var prcs = process.curl.open("-o test.json http://httpbin.org/anything/test");

//等待 curl 进程退�?prcs.waitOne();

/*
下面创建进程管道，返�?process.popen 对象�?不显�?curl 自带的控制台窗口，不显示 curl 操作进度�?*/

var prcs = process.curl.popen("http://httpbin.org/anything/test");

//等待 curl 进程退出，返回进程输出，进程错误输出，进程退出代�?var out,err,exitCode = prcs.readAll();

console.log(out);
console.pause(true);

/*
curl 文档�?https://curl.se/docs/manual.html
https://curl.se/docs/manpage.html
*/

/*
更推荐使�?web.rest （体积小，基于系统自带组件，用法更简单）
https://mp.weixin.qq.com/s/4mYRDnO49alwpQoBD_cILg

或使�?inet.http  （体积小，基于系统自带组件，用法更简单）
https://mp.weixin.qq.com/s/3Xp4c1LxsOQJsux5o8bhvA
*/

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/curl/process.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/curl/process.md')

