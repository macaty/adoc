[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 监视资源管理�?changeNotification

```aardio aardio
//监视资源管理�?changeNotification
import win.ui;
/*DSG{{*/
var winform = win.form(text="请拖动需要监视的文件到下面的文件列表�?;right=599;bottom=399;max=false)
winform.add(
btnWatch={cls="button";text="开始监�?;left=332;top=166;right=484;bottom=203;z=2};
lvChange={cls="listview";left=16;top=212;right=579;bottom=384;acceptfiles=1;bgcolor=16777215;edge=1;z=3};
lvFile={cls="listview";left=18;top=12;right=581;bottom=160;acceptfiles=1;bgcolor=16777215;edge=1;z=1}
)
/*}}*/

import win.util.changeNotification;
changeNotification = win.util.changeNotification(winform);

changeNotification.onMakeDir = function(srcPath,dstPath){
     winform.lvChange.addItem( {srcPath;"创建目录"} )
}
changeNotification.onCreate = function(srcPath,dstPath){
     winform.lvChange.addItem( {srcPath;"创建文件"} )
}
changeNotification.onRenameItem = function(srcPath,dstPath){
     winform.lvChange.addItem( {srcPath;"重命名文�?} )
}
changeNotification.onRenameFolder = function(srcPath,dstPath){
     winform.lvChange.addItem( {srcPath;"重命名目�?} )
}
changeNotification.onDelete = function(srcPath,dstPath){
     winform.lvChange.addItem( {srcPath;"删除文件"} )
}
changeNotification.onRemoveDir = function(srcPath,dstPath){
     winform.lvChange.addItem( {srcPath;"删除目录"} )
}
changeNotification.onUpdateDir = function(srcPath,dstPath){
     winform.lvChange.addItem( {srcPath;"目录下的文件已被改动"} )
}

winform.btnWatch.oncommand = function(id,event){
    if( winform.btnWatch.text == "开始监�?){
        changeNotification.deregister();
        changeNotification.register();
        winform.btnWatch.text = "停止监视";
    }
    else {
        changeNotification.deregister()
        winform.btnWatch.text = "开始监�?;
    }
}

winform.lvFile.wndproc = {
    [0x233/*_WM_DROPFILES*/] = function(hwnd,message,wParam,lParam){
        var files = win.getDropFile(wParam)
        for(i=1;#files;1){
            winform.lvFile.addItem(files[i])
            changeNotification.watch(files[i],true);
        }
    }
}

winform.lvFile.insertColumn("文件",-1)
winform.lvChange.insertColumn("文件",100)
winform.lvChange.insertColumn("状�?,100)
winform.lvChange.fillParent(1);

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/Monitor/win.util.changeNotification.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/Monitor/win.util.changeNotification.md')

