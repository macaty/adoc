[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: main

```aardio aardio

<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>aardio宓屽叆electron婕旂ず</title>
  </head>

  <body>

   <h2 onmousedown="aardio.hitCaption();return false;"
        style="-webkit-user-select: none;cursor:default;">鎸夎繖閲岃皟鐢╝ardio.hitCaption()鎷栧姩绐楀彛!</h2>

   <button onclick="aardio.exit();">鐐硅繖閲岃皟鐢╝ardio鍏抽棴绐楀彛</button> <br><br>

   <button id="aardio">鐐硅繖閲岃窡aardio浜掕皟涓�涓嬪嚱鏁?/button><br><br>

    <?
    response.write("鍦╡lectron涓墽琛宎ardio浠ｇ爜")
    ?>

    </body>

    <script type="text/javascript">

    /*瀵煎叆aardio涓殑app.external 瀵硅薄*/
    aardio = require("aardio");

    /*鍝嶅簲鎸夐挳鐐瑰嚮浜嬩欢*/
    document.querySelector("#aardio").onclick = function(e){

        //璋冪敤aardio涓殑鍑芥暟,hello瑕佽皟鐢ㄧ殑鍑芥暟鍚嶅瓧,鍚庨潰鍙互璺熶换鎰忎釜璋冪敤鍙傛暟
        aardio.ex.hello( "浣犵偣鍑讳簡" + e.target.innerHTML,1,2,3,"鏈夊嚑涓弬鏁板啓鍑犱釜" )
            .then(
                function(message){
                    document.getElementById("aardio").innerText = "aardio杩斿洖鍊? + message;
                }
            )
    }

    /*鍝嶅簲aardio鏈嶅姟绔彂璧风殑璋冩煡浠诲姟*/
    aardio.on("getUrl",function(){
        return document.location.href;
    });

    </script>

</html>

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Electron/res/main.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Electron/res/main.md')

