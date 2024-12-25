[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 拖放节点演示

```aardio aardio
//拖放节点
import win.ui;
/*DSG{{*/
var winform = win.form(text="拖放节点演示";right=599;bottom=399)
winform.add()
/*}}*/

import web.layout;
var wbLayout = web.layout(winform,0xFFFF/*_HL_HANDLE_ALL*/);

wbLayout.html = /**
<select id="source" size="5">
  <option>拖动项目一</option>
  <option>拖动项目�?/option>
  <option>拖动项目�?/option>
</select>

<div id="destination">拖动上面的项目节点到这里</div>
**/

wbLayout.css = /**
select#source > option{
  draggable:only-move; /*设置拖动模式�?only-move 表示仅拖动节�?设为 copy-move 则允许拖动并复制节点*/
}

#destination{
  accept-drop: selector( select#source > option ); /*这里用CSS选择器指定什么节点可以被拖放到此容器�?/
  drop: append;/* 被放入此容器的节点的插入方式,append表示追加到子节点尾部,prepend插入头部,insert表示插入当前位置,recycle表示删除节点 */
  width:300px;
  height:100px;
  background:#ccc;
  padding:5px;
}

/*正在被拖动的项目激活此样式*/
option:moving {
  background:blue;
  color:white;
  opacity:0.5;
}

/*当节点拖动到接受拖放的容器上方时,下面的CSS高亮边框*/
div:drag-over {
  outline: 1px solid green;
}

/* 在开始拖动以�?所以能接受拖放的节点激活此状态并应用此样�?*/
div:drop-target {
  background: yellow;
}

**/

wbLayout.onMouseMove = function (ltTarget,ltOwner,x,y,ltMouseParams) {
    if( ltMouseParams.isdragging ){
        var ltDragging = web.layout.element( ltMouseParams.dragging );
    }
}

wbLayout.onDragEnter = function (ltTarget,ltOwner,x,y,ltMouseParams) {
    winform.text = "拖入容器 " + ltTarget.outerHTML
}

//拖动源节点时触发此事�?return true 阻止拖动
wbLayout.onDragRequest = function (ltTarget,ltOwner,x,y,ltMouseParams) {
    winform.text = "开始拖�?" + ltTarget.outerHTML
}

wbLayout.onDragLeave = function (ltTarget,ltOwner,x,y,ltMouseParams) {
    winform.text = "拖离容器 " + ltTarget.outerHTML
}

wbLayout.onDrop = function (ltTarget,ltOwner,x,y,ltMouseParams) {
    winform.text = "放下 " + ltTarget.outerHTML;
}

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/drag.md)

