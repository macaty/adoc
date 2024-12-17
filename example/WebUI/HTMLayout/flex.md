[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 娴忚鍣ㄤ几缂╃洅涓嶩TMLayout甯冨眬璇硶瀵规瘮

```aardio aardio
//浼哥缉鐩?import win.ui;
/*DSG{{*/
var winform = win.form(text="娴忚鍣ㄤ几缂╃洅涓嶩TMLayout甯冨眬璇硶瀵规瘮";right=759;bottom=469)
winform.add()
/*}}*/

import web.layout;
var wbLayout = web.layout(winform)

import process;
wbLayout.sinking = {
    onHyperlinkClick = function (ltTarget,ltEle,reason,behaviorParams) {
        process.openUrl(ltTarget.href);
        return true;
    }
}

wbLayout.html = /**
<html><head>
<title>娴忚鍣ㄤ几缂╃洅涓?HTMLayout 甯冨眬璇硶瀵规瘮</title>
<style>
div.section {
    margin: 1em;
}

div.section > div {
    font: 10pt Verdana, sans-serif;
    padding: 1em;
    text-align: center;
    width: 30%
}

div.section > pre {
    padding: 1em;
    border: thin solid #ddd;
    height: *
}

div.section > :nth-child(1) {
    background: #eff;
    width: 30%
}

div.section > :nth-child(2) {
    background: #ffe;
    width: 30%
}

div.section > .parent {
    border: thin solid #888;
}

div.section > .parent > .child {
    font-size: 28px;
    border: thin solid #bbb;
    text-align: center;
    background: gold;
}

div.section div {
}

div.section {
    flow: horizontal;
}

div.section > * {
    width: 1*;
    margin: 1em;
}

#A .parent {
    flow: horizontal;
}

#B .parent {
    flow: vertical;
}

#C .parent {
    flow: h-flow;
}

#C .parent .child {
    width: 40%;
}

#D .parent {
    flow: horizontal;
    border-spacing: *;
}

#E .parent {
    flow: horizontal;
    height: *;
}

#E .child {
    height: *;
    width: 40px
}

#E .child:nth-child(3) {
    height: 80px;
}

#F .parent {
    flow: horizontal;
    height: *;
}

#F .child {
    margin-top: *;
    margin-bottom: *;
}

#F .child:nth-child(3) {
    margin-top: 0;
    margin-bottom: *;
}

#G .parent {
    flow: horizontal;
}

#G .child {
    height: *;
    width: 40px
}

#G .child:nth-child(3) {
    width: *;
}
        </style>
    </head>
    <body>

<h1>娴忚鍣?<code>display:flex</code> 涓?HTMLayout/Sciter 甯冨眬璇硶 <code>flow/flex</code> 瀵规瘮</h1>
<a href="http://bbs.aardio.com/forum.php?mod=viewthread&tid=7159">鍙傝�冿細HTMLayout甯冨眬鏁欑▼</a>
<div .section id="header">
  <div>娴忚鍣? Flexbox </div>
  <div>HTMLayout/Sciter: flow/flex</div>
  <div>婕旂ず</div>
</div>

<h5>姘村钩甯冨眬</h5>
<div .section id="A">
  <pre>.parent {
  display:flex;
  flex-direction: row;
}</pre>
  <pre>.parent { flow:horizontal; }</pre>
  <div class="parent">
    <div class="child">1</div>
    <div class="child">2</div>
    <div class="child">3</div>
    <div class="child">4</div>
  </div>
</div>

<h5>鍨傜洿甯冨眬</h5>
<div .section id="B">
  <pre>.parent {
  display:flex;
  flex-direction: column;
}</pre>
  <pre>.parent { flow:vertical; }</pre>
  <div class="parent">
    <div class="child">1</div>
    <div class="child">2</div>
    <div class="child">3</div>
    <div class="child">4</div>
  </div>
</div>

<h5>姘村钩娴佸紡甯冨眬</h5>
<div .section id="C">
  <pre>.parent {
  display: flex;
  flex-wrap: wrap;
}
.child {
  width:40%;
} </pre>
  <pre>.parent {
  flow:h-flow;
}
.child {
  width:40%;
}</pre>
  <div class="parent">
    <div class="child">1</div>
    <div class="child">2</div>
    <div class="child">3</div>
    <div class="child">4</div>
  </div>
</div>

<h5>姘村钩甯冨眬锛屽苟骞冲垎闂磋窛</h5>
<div .section id="D">
  <pre>.parent {
  display:flex;
  flex-direction: row;
  justify-content: space-between;
}</pre>
  <pre>.parent {
  flow:horizontal;
  border-spacing:*;
}</pre>
  <div class="parent">
    <div class="child">1</div>
    <div class="child">2</div>
    <div class="child">3</div>
    <div class="child">4</div>
  </div>
</div>

<h5>姘村钩甯冨眬锛岄珮搴﹁嚜閫傚簲</h5>
<div .section id="E">
  <pre>.parent {
  display:flex;
  flex-direction: row;
  height:80px;
  align-items:stretch;
}
.child:nth-child(3) {
  align-self: flex-start;
}</pre>
  <pre>.parent {
  flow:horizontal;
  height:*;
}
.child {
  height:*;
  width:40px
}
.child:nth-child(3) {
  height:80px;
}</pre>
  <div class="parent">
    <div class="child">1</div>
    <div class="child">2</div>
    <div class="child">3</div>
    <div class="child">4</div>
  </div>
</div>

<h5>姘村钩甯冨眬锛屽瀭鐩村榻?/h5>
<div .section id="F">
  <pre>.parent {
  display:flex;
  flex-direction: row;
  height:80px;
  align-items:center;
}
.child:nth-child(3) {
  align-self: flex-start;
}</pre>
  <pre>.parent {
    flow: horizontal;
    height: *;
}
.child {
    margin-top: *;
    margin-bottom: *;
}
.child:nth-child(3) {
    margin-top: 0;
    margin-bottom: *;
}</pre>
  <div class="parent">
    <div class="child">1</div>
    <div class="child">2</div>
    <div class="child">3</div>
    <div class="child">4</div>
  </div>
</div>

<h5>姘村钩甯冨眬锛屽搴﹁嚜閫傚簲</h5>
<div .section id="G">
  <pre>.parent {
  display:flex;
  flex-direction: row;
}
.child:nth-child(3) {
  flex: 1;
}</pre>
  <pre>.parent { flow:horizontal; }
.child { height:*;width:40px  }
.child:nth-child(3) { width: *; }</pre>
  <div class="parent">
    <div class="child">1</div>
    <div class="child">2</div>
    <div class="child">3</div>
    <div class="child">4</div>
  </div>
</div>
</body></html>
**/

winform.show(3/*_SW_MAXIMIZE*/)
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/flex.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/flex.md')

