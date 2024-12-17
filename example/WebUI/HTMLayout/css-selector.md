[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: HTMLayout 选项卡控�? tabs behavior应用 )

```aardio aardio
//选项�?/*
HTMLayout 选项卡控件使用教�?http://www.aardio.com/thread-8503-1-1.html
*/

import win.ui;
/*DSG{{*/
var winform = win.form(text="HTMLayout 选项卡控�? tabs behavior应用 )";right=599;bottom=399;)
winform.add()
/*}}*/

import web.layout;
import web.layout.behavior.tabs; //导入behavior
var wbLayout = web.layout(winform)

wbLayout.html = /**
<html>
<head>
<style>
body{
    margin:0;
    background:#e67259;
    padding:2px;
}
.tabs
{
  font:system;
  behavior:tabs; /*指定这是一个选项卡控�?/
  flow: horizontal; /*修改默认的垂直布局为横向布局,这样strip就跑左侧去了*/
  height:100%%;
  width:100%%;
  overflow:hidden;
}

.tabs > .strip /* 选项卡容�?*/
{
  flow: vertical; /*选项卡按钮改成垂直布局*/
  margin-bottom:-1px;
  padding: 4px 0 2px 2px;
  width:120px;
  height:100%;
  background:#e67259;
}

.tabs > .strip > [panel] /* 选项卡按钮默认样�?*/
{
  padding: 3px;
  margin-bottom:1px;
  height: max-intrinsic;
  background:#e67259;
  text-align:right;
  position: relative;
}
.tabs > .strip > [panel] span{
    margin-right:15px;
}
.tabs > .strip > [panel]:hover /* 鼠标悬停选项卡样�?/
{
  background-color:#e67259 rgb(236,240,241) rgb(236,240,241) #e67259;
  transition:blend;
}
.tabs > .strip > [panel]:current  /*当前选项卡样�?/
{
  background-color:#FFF;
  position:relative;
}
.tabs > .strip > [panel]:current:hover /*点击当前选项卡的样式*/
{
  transition:none;
}

.tabs > .strip > [panel]:current:first-child,
.tabs > .strip > [panel]:current:hover:first-child
{
}

.tabs:focus .strip [panel]:current
{
}

//下面指定内容页样�?.tabs > .panel[name] { display:none; }

//框架页正在打开
.tabs > iframe.panel[name]:busy {
  foreground-image:url(images/loading.png);
  foreground-repeat: no-repeat;
  foreground-position: 2px 2px;
}

.tabs > .panel[name]:expanded
{
  background:#FFF;
  padding:7px;
  margin:0;
  display:block;
  height:100%%;
  width:100%%;//框架必须指定宽度
}

//下面指定关闭按钮的样�?.tabs > .strip > [panel] .close-panel{
  display:none;
}
.tabs > .strip > [panel]:current .close-panel{
  display:block;
  position: absolute;
  top:6px;
  right:2px;
  width:12px;
  height:12px;
  line-height: 12px;
  border-radius:12px;
  font-size: 12px;
  font-family:"Marlett";
  color: #7e8c8d;
  content:"r";
}
.tabs > .strip > [panel]:current .close-panel:hover{
  background:#999;
  color: #FFF;
}
.tabs > .strip > [panel]:current .close-panel:active{
   background:red;
   color: #FFF;
}
</style>
</head>

<body>
   <div class="tabs"  >

      <div class="strip" >
        <!-- 选项�?可以随意放到哪一�?必须使用DIV标签 -->
         <div panel="panel1" selected><span>选项一</span></div>
         <div panel="panel2"><span>选项�?/span></div>
         <div panel="panel3"><span>选项�?/span></div>
      </div>

      <div class="panel"  name="panel1">
          在超链接的URL前面加上tabs://的前缀,例如<br />
         <a href="tabs://about:blank" title="新页�? target="_blank">tabs://about.html</a> <br /><br />
          然后在超链接�?title属性中指定新建选项卡的标题,<br />
          最后指定用target属性指定目标选项卡的名字,"_blank"表示新建选项�?<br />

          符合以上条件的超链接 - 点击则会在选项卡页面中打开,<br /><br />
          这种动态创建的选项�?默认会添加一个关闭按�? 注意这个按钮在CSS中要指定 float:right 以向右浮�?      </div>
      <div class="panel"  name="panel2">
          这是第二个选项�?其中name属性指定选项卡名�?          <button>按钮</button>
      </div>
      <div class="panel" name="panel3">
          这是第三个选项�?其中name属性指定选项卡名�?          <button #my-button>点这�?/button>
      </div>
   </div>
</body>
</html>
**/

//切换选项页激活下面的事件
import console;
wbLayout.onElementExpanded = {
    panel1  =  function (ltTarget,ltEle,reason) {
        console.dump( ltTarget.outerHTML );
    };
    panel2 =  function (ltTarget,ltEle,reason) {
        console.dump( ltTarget.outerHTML );
    };
    panel3 =  function (ltTarget,ltEle,reason) {
        console.dump( ltTarget.outerHTML );
    };
    /*
    HTMLayout的回调事件即可以是函�?也可以是一个函数表�?    函数表的键即节点的id或name属�?如果没有匹配名称的函�?则调用default函数
    */
    default = function(ltTarget,ltEle,reason){
        console.dump( ltTarget.name );
    };
}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/css-selector.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/css-selector.md')

