[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: RPC 服务�?- 支持任意本地网页调用 aardio 函数

```aardio aardio
//external 服务�?import win.ui;
/*DSG{{*/
var winform = win.form(text="RPC 服务�?- 支持任意本地网页调用 aardio 函数";right=759;bottom=469)
winform.add(
edit={cls="richedit";left=23;top=24;right=730;bottom=446;edge=1;hscroll=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

import web.rpc.externalServer;
var externalServer = web.rpc.externalServer();

//只有下面指定的函数网页才能调�?externalServer.external = {
    test = function(...){
        winform.edit.print("external.test 被调�?,...)
    }
    tag = function(strs,...){
        var args = {...}
        for(i=#args;1;-1){
            table.insert(strs,args[i],i+1);
        }

        strs = string.join(strs);
        return strs;
    }
}

//可选用下面的方法限定只有下面允许的外部域名才能访问 aardio 函数
externalServer.accessControlAllowOrigin = {
    ["https://d.aardio.com"] = true //指定准确前缀，域名后不要加斜�?}

//如果不指定端口号，则默认动态分配空闲的端口�?//如果不指定具体的端口号，则只�?externalServer 提供的网页才能自 aardio.js 自动获取到端口号
winform.edit.print( "启动服务器：",externalServer.start())
winform.edit.print( "请在网页中引入：",externalServer.getUrl("aardio.js"))

externalServer.httpHandler["/test.html"] = function(response,request){
    var html = /**
    <!doctype html>
    <html>
    <head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge" />
        <script src="<?=owner.rpcUrl?>"></script>
        <script>
        /*
        也可以在前端源码中用 npm i aardio 安装 aardio.js �?        externalServer 提供�?aardio.js 自动获取 RPC 端口并初始化 RPC 方法�?        如果在创�?web.rpc.externalServer 以后调用标准库中�?nodeJs 创建 Node.js  进程�?        也可以自动获取端口号并在连接成功前创建远程函数�?
        远程服务器上的网页可通过 URL 参数获取 RPC 端口并初始化 RPC 方法�?        也可以调�?aardio.open( 端口�?) 连接指定的端口�?        可参考：https://d.aardio.com/ajs/demo.html
        */

        //调用 aardio 函数�?        aardio.test("这是网页调用 aardio 的参�?,1122);

        //�?aardio 解析模板字符�?        let $ = aardio.tag;
        $`abc${123}ddd${456}`.then( v=> alert("模板字符�?"+v)  )

        </script>
    </head>
    <body><?=owner.rpcUrl?></body></html>
    **/
    response.write( string.loadcode(html,{rpcUrl=externalServer.getUrl("aardio.js")}) );
}

import process;
process.openUrl(externalServer.getUrl("/test.html"))

/*
如果传入小写 http: �?https: 开头的网址�?则返回了附加 rpcServerPort �?rpcAasdl 参数的网址�?aardio.js 识别这些参数后自动获�?RPC 端口并初始化 RPC 方法�?
未传以上参数则网页中必须调用 aardio.open 连接指定的端口�?*/
var rpcUrl = externalServer.getUrl("https://d.aardio.com/ajs/demo.html");
process.openUrl( rpcUrl );

//上面 demo.html 的源码如下：
/**
<!doctype html>
<html><head>
    <meta charset="utf-8">
    <script src="https://d.aardio.com/ajs/aardio.js"></script>
    <script type="text/javascript">
        (async () => {
            /*
            aardio.js 可自动从网址参数 rpcServerPort，rpcAasdl 获取并连接端口与所有远程函数�?            如果未指定参数，则应调用 aardio.open( RPC端口�?) 打开 RPC 服务器�?            aardio.open 返回 Promise 对象�?
            连接成功前只能使�?aardio.xcall 调用本地函数�?            */
            //await aardio.open(8082);

            await aardio.test("这是网页调用 aardio 的参�?, 1122);

            let $ = aardio.tag;
            $`abc${123}ddd${456}`.then(v => alert("模板字符�?" + v));
        })()
    </script>
</head><body></body></html>
**/

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/RPC/externalServer.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/RPC/externalServer.md')

