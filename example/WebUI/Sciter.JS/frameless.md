[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: Sciter 无边框窗�?
```aardio aardio
//无边框窗�?import win.ui;
/*DSG{{*/
var winform = win.form(text="Sciter 无边框窗�?;right=759;bottom=469;border="none")
winform.add()
/*}}*/

import web.sciter;
import web.sciter.behavior.windowCommand;
var sciter = web.sciter( winform );

//开发环境中启用sciter调试功能
if( _STUDIO_INVOKED ){
    import web.sciter.debug;
    sciter.attachEventHandler( web.sciter.debug );
}

sciter.html = /**
<!doctype html>
<html><head><META http-equiv="Content-Type" content="text/html; charset=utf-8"></head>
<body>
    <!-- 界面顶栏 -->
    <div id="header">

        <!-- 下面是标题栏按钮,必须使用a标记表示,command属性指示该按钮执行的命�?可在窗体设计器中禁用最大化、最小化按钮 -->
        <div class="titlebox">
            <a command="window-min">0</a><a command="window-max">1</a><a command="window-close" >r</a>
        </div>

        <!-- 标题栏弹出菜�?需要弹出节点的最好用div或button等元�?不要使用a,li等元�?-->
        <div .window-menu>u
            <menu .popup> <!-- .popup是内置的弹出菜单样式 -->
                <li>在线帮助</li>
                <li>子菜�?                <menu >
                    <li>这是子菜�?/li>
                </menu>
                </li>
                <li #exit>退�?/li>
            </menu>
        </div>

        <!-- 下面是标题栏文本,凡在CSS中指�?behavior:windowCommand 的节�?含子节点) 可用 command 属性指明命令类�?-->
        <div class="title-bar" command="window-caption"> <span class=title> �?�?�?�?</span></div>
    </div>

    <!-- 界面中部内容�?-->
    <div id="container">

        <!-- 左边�?固定宽度 -->
        <div class="lside"> </div>

        <!-- 右边�?自适应宽度 -->
        <div class="rside"> </div>
    </div>

    <!-- 界面底栏 -->
    <div id="footer">
        <button id="help">Sciter 布局教程</button>
    </div>
</body>
</html>
**/

sciter.css = /**
html,body{
    margin:0; /*去掉默认的页面边�?/
    height:100%;/*因为HTML元素的高度默认是按需增加�?所有需要显示指定根节点高度*/
    background:#fff;/*网页背景�?/
}

body{
    overflow:hidden;/*避免出现滚动�?/
}

/*最大化后body会自动添加maximize属�?如果是圆角界面可以在这里移除圆角*/
body[maximize]{
    border-radius:0;
}

body[maximize] #header{
    border-radius:0;
}

#header{
    height:32px;
    background:rgb(52,152,220);
    cursor:default;
    behavior:windowCommand;
    overflow:hidden;/*清除浮动*/
}

#header .title-bar{
    margin-right:95px;
    padding:8px 5px 5px 15px;
    height:28px;
    line-height: 28px;
    font:system;
    color:#fff;
}

#header .titlebox{
    width:max-intrinsic;
    height:28px;
    float:right;
    margin-right:8px;
    overflow-x:hidden;
}

#header .titlebox a{
    display:inline-block; //显示为块节点
    width:max-intrinsic;
    height:14px;
    font-family:"Marlett";/*该字体显示按钮符�?/
    font-size:14px;
    padding:4px;
    color:#fff;
    cursor:default;
}

/*CSS选择器中,方括号指定节点拥有的属�?/
#header .titlebox a[command]:hover{
    background:#6ebccf;
}

#header .titlebox a[command]:active{
    background:#FF0000;
}

#header a[command="window-restore"]{
    content:"2";/*Marlett字体为还原按钮符�?/
}

#header .window-menu{
    display:block;
    float:right;
    text-align:right;
    behavior:button popup-menu;
    width:16px;
    height:14px;
    font-family:"Marlett";/*该字体显示按钮符�?/
    font-size:14px;
    padding:4px;
    color:#fff;
}

#header .window-menu:hover{
    background:#6ebccf;
}

#header .window-menu:owns-popup /*菜单已弹�?/
{
    background-color: #FF0000;
    color: #FFFFFF;
}

#container{
    width:100%;
    height:100%%; /*撑满剩余可用空间*/
    flow: horizontal; /*将容器内部块元素变为横向布局 - 比具有破坏性的float浮动布局更方�?/
    margin:0 auto;
    overflow:hidden;
    background:#ac0;
}

#container .lside{
    height:100%%;
    width:150px;
    background:rgb(110,179,210);
}

#container .rside{
    height:100%%;
    width:100%%;
    background:#FFF;
}

#container .lside > *{
    margin:38px 0px;
}

#container .rside > *{
    margin:38px 10px;
    font-size:9pt;
}

#footer {
    background:rgb(239,237,238);
    height:25px;
    text-align:right;
    padding:10px 20px;
}

#footer button{
    padding:4px 13px;
    font-size:12px;
    background:rgb(27,174,93);
    color:white;
}

#footer button:hover {
    background:rgb(33,127,188);
    outline: 1px glow rgb(91,171,230) 1px;
    cursor:pointer;
}
**/

// 响应菜单点击事件
sciter.onMenuItemClick =  {

    // 事件可以是一个函数或列表,如果是列表键名匹配节点的id或name属�?    exit = function (scTarget,scOwner,reason,behaviorParams) {
        winform.close();
    }

    //匹配不到id的节点会触发default函数*/
    default = function (scTarget,scOwner,reason,behaviorParams) {
        var ltPopupOwner = web.sciter.element( behaviorParams.he );//这是弹出菜单的按钮节�?        winform.msgbox( scTarget.innerText )
    }
}

import process;
sciter.onButtonClick = {
    help = function (scTarget,scOwner,reason,behaviorParams) {
        process.execute("http://api.aardio.com/v10/pages/htmlayout-introduction");
    }
}

import win.ui.shadow;
win.ui.shadow(winform); //添加阴影边框

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/frameless.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/frameless.md')

