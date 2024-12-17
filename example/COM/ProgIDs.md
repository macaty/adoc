[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 系统已注�?COM 类名列表�?点列标题排序，双击列显示编辑框，右键菜单查看对象文档 �?
```aardio aardio
//COM 类名列表
import win.ui;
import win.ui.menu;
import fonts.fontAwesome;
/*DSG{{*/
var winform = win.form(text="系统已注�?COM 类名列表�?点列标题排序，双击列显示编辑框，右键菜单查看对象文档 �?;right=1109;bottom=656;bgcolor=16777215;)
winform.add(
listview={cls="listview";left=17;top=40;right=1094;bottom=640;acceptfiles=1;asel=false;bgcolor=16777215;db=1;dl=1;dr=1;dt=1;edge=1;font=LOGFONT(name='SimSun');fullRow=1;gridLines=1;hide=1;msel=false;z=1};
plusLoading={cls="plus";left=372;top=188;right=743;bottom=450;color=15780518;db=1;dl=1;dr=1;dt=1;font=LOGFONT(h=-96;name='FontAwesome');iconStyle={font=LOGFONT(h=-96;name='FontAwesome')};iconText='\uF254';z=2};
plusSearch={cls="plus";left=690;top=6;right=1094;bottom=36;align="right";autohscroll=false;autovscroll=false;border={bottom=1;color=-4144960};dr=1;dt=1;editable=1;font=LOGFONT(h=-13);hide=1;textPadding={top=10;bottom=3};valign="top";z=3}
)
/*}}*/

winform.listview.insertColumn("类名",250)
winform.listview.insertColumn("CLSID",250)
winform.listview.insertColumn("控件",70)
winform.listview.insertColumn("描述",70)
winform.listview.insertColumn("路径",-1)

thread.invoke(
    function(winform){
        import win.reg;
        import win.guid;

        winform.plusLoading.hide = false;
        winform.plusSearch.hide = true;
        winform.listview.hide = true;
        winform.plusLoading.disabledText = {'\uF254';'\uF251';'\uF252';'\uF253';'\uF250'}

        var items = {};
        var progIds = {}
        var onOpenRegClsId = function(regClsId,clsId){
            var regClsIdProgId = regClsId.open("ProgID",true)
            if(regClsIdProgId){

                var progId = regClsIdProgId.queryValue("")
                if(progId && !progIds[progId]){
                    progIds[progId] = true;

                    var description;
                    var regProgId = win.regReader("HKEY_CLASSES_ROOT\"+progId)
                    if(regProgId){
                        description = regProgId.queryValue("");
                        regProgId.close();
                    }

                    var path
                    var regServer32 = regClsId.open("InprocServer32",true) || regClsId.open("LocalServer32",true)
                    if(regServer32){
                        path = regServer32.queryValue("");
                        regServer32.close();
                    }

                    var clsIdKeys = regClsId.keys();
                    table.push(items,{progId;clsId;
                                (table.find(clsIdKeys,"Control")||table.find(clsIdKeys,"ToolboxBitmap32"))?"�?:"�?;
                                description||"";
                                path||"";
                    });
                }
                regClsIdProgId.close()
            }
            regClsId.close()
        }

        var clsIds = {}
        var reg = win.regReader("HKEY_CLASSES_ROOT\CLSID\")
        for(clsId,writetime in reg.eachKey() ){
            if(!string.match(clsId,"%{}")){
                continue ;
            }

            try{
                var regClsId = reg.open(clsId,true);
                if(regClsId) onOpenRegClsId(regClsId,clsId);
                clsIds[clsId] = true;
            }
        }

        var reg = win.regReaderWow64("HKEY_CLASSES_ROOT\CLSID\")
        for(clsId,writetime in reg.eachKey() ){
            if(!string.match(clsId,"%{}")){
                continue ;
            }

            if(clsIds[clsId]){
                continue ;
            }

            try{
                var regClsId = reg.open(clsId,true);
                if(regClsId) onOpenRegClsId(regClsId,clsId);
            }
        }

        ..table.sort(items,lambda(a) owner[1]<a[1])
        winform.listview.items = items;
        winform.listview.itemData = items;
        winform.listview.itemSortColumn = 1;
        winform.plusLoading.disabledText = null;
        winform.plusLoading.hide = true;
        winform.listview.hide = false;
        winform.plusSearch.hide = false;
        winform.plusSearch.setFocus();
    },winform
)

import win.imageList;
var iml = win.imageList(16, 15);
iml.add('GIF\56\57a \0\15\0\x80\0\0\x80\x80\x80\xff\0\xff\33\xf9\4\0\0\0\0\0\44\0\0\0\0 \0\15\0\0\2\31\x8c
\x8f\xa9\xcb\xed\15\xa3\x9c\xb4N\xf0\x80\xde\56k\xbfA\\\xd7\x84 \x97Y\xea\xca\xb6\xee\11\xc7F\1\0;', 0xff00ff);
winform.listview.setColumnImageList(iml);

var reloadItemData = function(){
    var sortColumn = winform.listview.itemSortColumn;
    var word = string.trim(winform.plusSearch.text);
    var itemData = winform.listview.itemData;
    if(#word){
        word = "@@" + word;
        itemData = table.filter(itemData
                ,lambda(v) string.find(v[1],word) || string.find(v[2],word) || string.find(v[4],word) || string.find(v[5],word) )
    }

    if(sortColumn<0){
        var i = math.abs(sortColumn)
        ..table.sort(itemData,lambda(a) owner[i]>a[i])
    }
    else {
        ..table.sort(itemData,lambda(a) owner[sortColumn]<a[sortColumn])
    }

    winform.listview.replaceItems(itemData)
}
winform.listview.enableDoubleBuffering();

import com.tlbDoc;
winform.popmenu = win.ui.popmenu(winform);//创建弹出菜单
winform.popmenu.add('创建控件并列出成�?,function(id){
    var clsId = winform.listview.getItemText( winform.listview.selIndex,2 );
    if(clsId){
        var obj = com.CreateObject(clsId)
        if(obj){
            import console
            console.setTitle("COM对象:" +  winform.listview.getItemText( winform.listview.selIndex,1 ) + " " + clsId)
            com.tlbDoc.dump(obj);
        }
    }
});

import win.ui.grid;
var grid = win.ui.grid(winform.listview);
/*
用户点击列头排序时会触发下面的事件，
column 为例号，desc 参数指定是否倒序，返�?true 允许当前列排�?*/
grid.onSortColumn = function(column,desc){
    winform.listview.itemSortColumn = desc ?-column : column;
    reloadItemData();
    return true;
}

//右键菜单
grid.onRightClick = function(){
    winform.popmenu.popup();
}

winform.plusSearch.setCueBannerText("输入类名关键字（支持模式匹配�?)

import win.debounce;
winform.plusSearch.editBox.onChange = win.debounce(function(){
    if(#winform.plusSearch.text) reloadItemData();
},500)

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/ProgIDs.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/ProgIDs.md')

