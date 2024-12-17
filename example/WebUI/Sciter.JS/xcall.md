[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: js 调用 aardio 自定义事�?
```aardio aardio
//JS 调用本地函数
import win.ui;
/*DSG{{*/
var winform = win.form(text="js 调用 aardio 自定义事�?;right=1014;bottom=523;)
winform.add()
/*}}*/

import web.sciter;
var sciter = web.sciter( winform );

//JS 调试输出发送到到控制台，支�?JS �?console.log()
import web.sciter.debug;
sciter.attachEventHandler( web.sciter.debug );

//�?web.sciter.behavior 名字空间添加自定�?behavior
namespace web.sciter.behavior.customEvent {

    //behavior 中名称不�?on 开始的函数都是自定义函�?    testJs = function(scOwner,str,jsCallback){
        import console
        console.log("behavior里的函数 testJs 被调用了");
        console.log("自定义函数接收到的第一个参数总是节点自身")
        console.log("然后才是其他参数",str)

        //aardio里调用behavior自定义函数的方法是一样的,提供一模一样的xcall函数
        scOwner.xcall("testJs2",str);

        //�?aardio 中能接收 Javascript 返回值的地方都支持直接返回Javascript 函数对象
        jsCallback("�?aardio 中能接收 Javascript 返回值的地方都支持直接返回Javascript 函数对象")
    }

    testJs2 = function(scOwner,...){
        console.log("behavior里的函数 testJs2 被调用了",...)
        console.log("自定义函数接收到的第一个参数总是节点自身")
        console.log(scOwner.outerHTML)
    }

    //JS 脚本中读�?value 时触发此回调，第2个返回值返�?value 的�?    onGetValue = function( ltOwner ){
        return true,"Value:onGetValue";
    }

    //JS 脚本中使用修�?value 值时触发此回�?    onSetValue = function(  ltOwner,value ){

        return true
    }
}

sciter.html = /**
<!doctype html>
<html>
<head>
    <META http-equiv="Content-Type" content="text/html; charset=utf-8">
    <style type="text/css">
    html,body{ height:100%; margin:50; }

    #my-button{
        behavior:"customEvent clickable";
    }
    </style>
</head>
<body>
<button id="my-button">调用 behavior 定义�?aardio函数：testJs </button>
<br> 请务必更�?web.sciter 扩展库到最新版�?
<script>

var button = document.getElementById("my-button");
button.addEventListener('click', () => {

    // 调用 aardio 函数, 请务必更�?web.sciter 扩展库到最新版�?    button.xcall("testJs", "hello",function jsCallback(argA){
        console.log("在aardio中调用了 Javascript 回调函数",argA)
    });
})

</script>
</body>
</html>
**/

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/xcall.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/xcall.md')

