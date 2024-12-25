[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: PHP CGI 回调 aardio

```aardio aardio
//PHP 回调 aardio
import process.php;
import win.ui;
/*DSG{{*/
var winform = win.form(text="PHP CGI 回调 aardio";right=753;bottom=434)
winform.add(
edit={cls="edit";left=20;top=12;right=734;bottom=404;edge=1;multiline=1;z=1}
)
/*}}*/

//注册多线程全局变量
process.php.threadGlobal = {
    winform = winform;
}

//自定�?HTTP 处理程序
process.php.httpHandle = {
    ["/jsonrpc"] = {
        //多线�?JSON RPC 服务端函数，支持不定个数参数
        hello = function(name,value){

            ..winform.edit.print("hello 函数�?PHP 调用�?参数�?,name,value);

            //第一个返回值为客户端返回�?result)，第二个返回值为错误对象(error)
            if(!name) return null,-32602/*_JSONRPC_INVALID_PARAMS*/;

            return "hello " + name;
        }
    }
}

process.php.code["/rpc-callback.php"] = /**<?php
ignore_user_abort(true); // 后台运行
set_time_limit(0); // 取消脚本运行时间的超时上�?
//可选在参数中指定服务端 URL 不指定参数则设为 'http://'.$_SERVER['HTTP_HOST'].'/jsonrpc';
$aardio = new JsonRpcClient();

//�?aardio 作服务端因不需要频繁创建进程，所以速度更快�?for ($i=1; $i<=20; $i++)
{
    // PHP 调用 aardio  函数
    $ret = $aardio->hello('param1',$i );
    /*
    建议使用 process.php.7.4 以上版本�?    不然 file_get_contents 偶尔失败会导�?JSON RPC 函数返回 null�?    PHP 7.x 或以上就没有问题，而且速度更快�?    */

    sleep(1);
}
?>**/

//启动 PHP 页面，不获取页面输出，不阻塞界面线程
process.php.notify("/rpc-callback.php"); //开发环境打开控制台可查看错误信息

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/PHP/rpc.callback.md)

