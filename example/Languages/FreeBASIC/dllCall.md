[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 DLL

```aardio aardio
//调用 DLL

//加载DLL,DLL路径前面加上$表示把DLL嵌入到程序中并通过内存加载
var dll = raw.loadDll(
    $"\basic.dll",,"cdecl" //注意参数里指定使�?cdecl 调用约定�?);

//定义结构体，当然也可以先声明一�?class 来创建实例�?var info = {
    int x;
    INT y;
}

// 然后直接调用 API
var ret = dll.msgboxW(123,456,"测试一下好用不好用",info);
/*
相关文档�?https://www.aardio.com/zh-cn/doc/library-guide/builtin/raw/directCall.html
相关范例：�?aardio 范例 / 调用其他语言 / C语言 �?*/

//最后打印结构体看一下�?import console;
console.log(ret);

console.dumpJson(info);
console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/FreeBASIC/dllCall.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/FreeBASIC/dllCall.md')

