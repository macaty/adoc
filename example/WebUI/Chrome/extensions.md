[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: Chrome 扩展查看工具

```aardio aardio
//Chrome 扩展查看工具
import win.ui;
import win.ui.menu;
/*DSG{{*/
var winform = win.form(text="Chrome扩展查看工具";right=1002;bottom=651;)
winform.add(
editPath={cls="edit";left=97;top=617;right=987;bottom=642;edge=1;multiline=1;z=2};
listview={cls="listview";left=13;top=12;right=991;bottom=601;acceptfiles=1;asel=false;bgcolor=16777215;dl=1;dr=1;edge=1;font=LOGFONT(name='SimSun');fullRow=1;gridLines=1;hscroll=1;msel=false;vscroll=1;z=1};
static={cls="static";text="路径�?;left=24;top=620;right=83;bottom=641;align="right";transparent=1;z=3}
)
/*}}*/

winform.listview.insertColumn("扩展�?,180)
winform.listview.insertColumn("版本",100)
winform.listview.insertColumn("描述",-1)

import chrome.extensions;
var extensionsData = chrome.extensions.get();

for(i=1;#extensionsData;1){
    var manifest = extensionsData[i];
    var hItem = winform.listview.addItem({manifest.name;manifest.version;manifest.description})
}

winform.popmenu = win.ui.popmenu(winform);//创建弹出菜单
winform.popmenu.add('复制完整路径',function(id){
    var externsion = extensionsData[winform.listview.selIndex];
    if(externsion){
        import win.clip;
        win.clip.write(externsion.fullpath)
    }
});
winform.popmenu.add('浏览',function(id){
    var externsion = extensionsData[winform.listview.selIndex];
    if(externsion){
        import process
        process.execute(externsion.fullpath)
    }
});

winform.listview.onnotify = function(id,code,ptr){

    select(code) {
        case  0xFFFFFF9B/*_LVN_ITEMCHANGED*/ {
            var nm = winform.listview.getNotifyMessage(code,ptr)
            if(winform.listview.selIndex){
                var externsion = extensionsData[nm.iItem];
                winform.editPath.text = externsion.fullpath
            }
        }
        case 0xFFFFFFFB/*_NM_RCLICK*/  {
            winform.popmenu.popup();
        }
    }
}

import win.ui.grid;
win.ui.grid(winform.listview);

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/Chrome/extensions.md)

