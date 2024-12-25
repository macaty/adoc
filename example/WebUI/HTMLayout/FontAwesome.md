[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: HTMLayout - FontAwesome图标字体

```aardio aardio
//图标字体
import win.ui;
/*DSG{{*/
mainForm = win.form(text="HTMLayout - FontAwesome图标字体";right=759;bottom=469;border="dialog frame")
mainForm.add()
/*}}*/

import web.layout;
import web.layout.fontAwesome;//可以根据需要编辑字体文件移除用不到的图�?wbLayout = web.layout( mainForm );

wbLayout.html = /**
<!doctype html>
<html><head></head><body>
<span style="font-size:60px;"><i class="fa fa-bell-o" /> 铃铛</span> <br>
<span style="color:red"><i class="fa fa-pencil-square fa-5x " /> 编辑</span><br>
<button><i class="fa fa-pencil"/> 编辑</button>
</body></html>
**/
//所有可用样式请访问官网 http://fontawesome.io/cheatsheet

mainForm.show()
wbLayout.querySelector("button").state.focus = false;

return win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/FontAwesome.md)

