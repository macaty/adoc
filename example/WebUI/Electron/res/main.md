[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: main

```aardio aardio

<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>aardio嵌入electron演示</title>
  </head>

  <body>

   <h2 onmousedown="aardio.hitCaption();return false;"
        style="-webkit-user-select: none;cursor:default;">按这里调用aardio.hitCaption()拖动窗口!</h2>

   <button onclick="aardio.exit();">点这里调用aardio关闭窗口</button> <br><br>

   <button id="aardio">点这里跟aardio互调一下函�?/button><br><br>

    <?
    response.write("在electron中执行aardio代码")
    ?>

    </body>

    <script type="text/javascript">

    /*导入aardio中的app.external 对象*/
    aardio = require("aardio");

    /*响应按钮点击事件*/
    document.querySelector("#aardio").onclick = function(e){

        //调用aardio中的函数,hello要调用的函数名字,后面可以跟任意个调用参数
        aardio.ex.hello( "你点击了" + e.target.innerHTML,1,2,3,"有几个参数写几个" )
            .then(
                function(message){
                    document.getElementById("aardio").innerText = "aardio返回�? + message;
                }
            )
    }

    /*响应aardio服务端发起的调查任务*/
    aardio.on("getUrl",function(){
        return document.location.href;
    });

    </script>

</html>

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/Electron/res/main.md)

