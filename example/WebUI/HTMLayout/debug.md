[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调试

```aardio aardio
//调试
import win.ui;
/*DSG{{*/
winform = win.form(text="aardio form";right=599;bottom=399;)
winform.add(
layoutWindow={cls="edit";left=10;top=12;right=580;bottom=382;db=1;dl=1;dr=1;dt=1;multiline=1;notify=1;z=1}
)
/*}}*/

import web.layout;
wbLayout = web.layout(winform.layoutWindow);

wbLayout.html =/***
<div id="my-button" >请点击这�?/div>
***/

 //小技�? 输入 wbLayout.debug() 可自动完成下面的代码
import web.layout.debug; //这句的作用是可使用控制台输出CSS内部错误
wbLayout.attachEventHandler( web.layout.debug ); //这句代码为CSSS!增加了全局函数 debug()

wbLayout.css = /**
#my-button{
  assigned!:
    debug("CSS脚本中调用debug函数","输出一个或多个�?)
  ;
}
**/

wbLayout.css = /**
#my-button{
  height 19px; //这里制造了一个CSS语法错误
}
**/

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/debug.md)

