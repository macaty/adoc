[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鑺傜偣缁戝畾浜嬩欢

```aardio aardio
//缁戝畾浜嬩欢
import win.ui;
/*DSG{{*/
winform = win.form(text="鑺傜偣缁戝畾浜嬩欢";right=599;bottom=399;)
winform.add()
/*}}*/

import web.layout;

//鍙傛暟 @1 鎸囧畾宓屽叆缃戦〉鐨勭獥鍙ｏ紙鍙互鏄?winform 鎴?static,custom 绛夋帶浠跺璞★級
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

    winform.text = ( ltOption.state.expanded ? "閫変腑(灞曞紑) " : "閫変腑 " )++ ltOption.innerText
}

//璋冪敤姝ゅ嚱鏁板惎鐢ㄤ簨浠跺嚱鏁?layoutEle.attachEventHandler();

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/attachEventHandler.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/attachEventHandler.md')

