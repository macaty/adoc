[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 PHP - SSE 涔?浜嬩欢娴侊紙event-stream锛?
```aardio aardio
//aardio 璋冪敤 PHP - SSE 涔?浜嬩欢娴侊紙event-stream锛?import win.ui;
/*DSG{{*/
var winform = win.form(text="PHP - event-stream";right=753;bottom=434)
winform.add(
edit={cls="edit";left=20;top=12;right=734;bottom=404;edge=1;multiline=1;z=1}
)
/*}}*/

//瀵煎叆 php 鎵╁睍搴?import process.php;

//鐢熸垚娴嬭瘯 PHP 鏂囦欢銆?process.php.code["/test-sse.php"] =/********
<?php
header("Content-Type: text/event-stream");
header("Cache-Control:no-cache,must-revalidate,no-store");
header("Pragma:no-cache"); //绂佹缂撳瓨
ignore_user_abort(true); //鍚庡彴杩愯
set_time_limit(0); //鍙栨秷鑴氭湰杩愯鏃堕棿鐨勮秴鏃朵笂闄?
while (true) {

  //鏈嶅姟鍣ㄤ簨浠舵帹閫?  echo "event: ping\n";
  $curDate = date(DATE_ISO8601);
  echo 'data: {"time": "' . $curDate . '"}';
  echo "\n\n"; //姣忎釜浜嬩欢浠?2 涓崲琛岀粨鏉?
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
            winform.edit.print("HTTP 鏈嶅姟绔帹閫佷簡浜嬩欢")
            winform.edit.print(message);
        } );

    },url,winform
)
winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/PHP/sse.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/PHP/sse.md')

