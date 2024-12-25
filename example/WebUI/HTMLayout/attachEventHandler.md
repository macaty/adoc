[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 节点绑定事件

```aardio aardio
//绑定事件
import win.ui;
/*DSG{{*/
winform = win.form(text="节点绑定事件";right=599;bottom=399;)
winform.add()
/*}}*/

import web.layout;

//参数 @1 指定嵌入网页的窗口（可以�?winform �?static,custom 等控件对象）
wbLayout = web.layout(winform);

wbLayout.html = /**
<!doctype html>
<html>
<head>
    <style type="text/css">
    html,body{ height:100%; margin:0; }
    body widget { size:*; }
    </style>
</head>
<body>
    <widget #dd type="tree" treelines>
    <option expanded >Metals
      <option>Alkaline Metals
        <option>Lithium <code>Li</code></option>
        <option>Sodium <code>Na</code></option>
        <option>Potassium <code>K</code></option>
      </option>
      <option expanded>Transition Metals
        <option>Scandium <code>Sc</code></option>
        <option>Titanium <code>Ti</code></option>
        <option>Vanadium <code>V</code></option>
      </option>
    </option>
    <option expanded>Halogens
        <option>Fluorine <code>F</code></option>
        <option>Chlorine <code>Cl</code></option>
        <option>Bromine <code>Br</code></option>
    </option>
  </widget>
</body>
</html>
**/

var layoutEle = wbLayout.getEle("dd")
layoutEle.onSelectSelectionChanged = function (ltTarget,ltOwner,reason,behaviorParams) {
    var ltOption = ..web.layout.element( behaviorParams.he );

    winform.text = ( ltOption.state.expanded ? "选中(展开) " : "选中 " )++ ltOption.innerText
}

//调用此函数启用事件函�?layoutEle.attachEventHandler();

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/attachEventHandler.md)

