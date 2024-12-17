[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: TLS/HTTPS

```aardio aardio
//TLS/HTTPS
import console.int;
console.showLoading("正在检�?TLS 版本");

import web.rest.jsonClient;
var http = web.rest.jsonClient();
var sslInfo = http.get("https://www.howsmyssl.com/a/check");
console.dumpJson(sslInfo);

console.log(sslInfo.tls_version);
console.log(sslInfo.rating);

/*
inet.http ,web.form, web.rest �?在低版本操作系统上会自动调用 inet.tls 设置 TLS 版本�?
Win10 及之后的系统默认是不用设置的�?但有些软件在新系统上错误地修敢了注册表，也会导致这些系统�?HTTPS 请求异常�?当然这个问题比较罕见，处理方法请查看 inet.tls 库源码中的说明�?
如果系统不支持目�?HTTPS 网址�?TLS 版本�?通常会返�?12157 错误（参�?aardio 工具 > 网络 >  HTTP 状态码检测）�?*/

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/inet/http/tls.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/inet/http/tls.md')

