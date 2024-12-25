[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 PHP - SSE �?事件流（event-stream�?
```aardio aardio
//aardio 调用 PHP - SSE �?事件流（event-stream�?import win.ui;
/*DSG{{*/
var winform = win.form(text="PHP - event-stream";right=753;bottom=434)
winform.add(
edit={cls="edit";left=20;top=12;right=734;bottom=404;edge=1;multiline=1;z=1}
)
/*}}*/

//导入 php 扩展�?import process.php;

//生成测试 PHP 文件�?process.php.code["/test-sse.php"] =/********
<?php
header("Content-Type: text/event-stream");
header("Cache-Control:no-cache,must-revalidate,no-store");
header("Pragma:no-cache"); //禁止缓存
ignore_user_abort(true); //后台运行
set_time_limit(0); //取消脚本运行时间的超时上�?
while (true) {

  //服务器事件推�?  echo "event: ping\n";
  $curDate = date(DATE_ISO8601);
  echo 'data: {"time": "' . $curDate . '"}';
  echo "\n\n"; //每个事件�?2 个换行结�?
  if (ob_get_level() > 0) ob_end_flush();
  flush();
  sleep(1);
}
?>********/

var url = process.php("/test-sse.php")

thread.invoke(
    function(url,winform){
        import web.rest.jsonLiteClient;
        var http = web.rest.jsonLiteClient();

        var eventSource = http.api(url,"GET")

        eventSource.get(,, function(message){
            winform.edit.print("HTTP 服务端推送了事件")
            winform.edit.print(message);
        } );

    },url,winform
)
winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/PHP/sse.md)

