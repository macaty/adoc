[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 多线程多文件断点续传下载

```aardio aardio
//多线程多任务
import win.ui;
/*DSG{{*/
var winform = win.form(text="多线程多文件断点续传下载";right=765;bottom=399)
winform.add(
button={cls="button";text="多线程多文件断点续传下载";left=478;top=356;right=703;bottom=392;db=1;dr=1;z=2};
listview={cls="listview";left=10;top=16;right=757;bottom=346;bgcolor=16777215;db=1;dl=1;dr=1;dt=1;edge=1;z=1}
)
/*}}*/

//初始化listview控件
winform.listview.insertColumn("网址",180);
winform.listview.insertColumn("文件�?,180);
winform.listview.insertColumn("状�?,100);
winform.listview.insertColumn("大小",80);
winform.listview.insertColumn("速度",80);
winform.listview.insertColumn("已下�?,120);
winform.listview.adjust = function(cx,cy){
    winform.listview.fillParent(1);
}

//创建下载线程管理�?import thread.dlManager;
var dlmgr = thread.dlManager(5/*最多允许五个线程同时下�?/);

//下载开始触�?dlmgr.onReceiveBegin = function(id,url,filename,statusText,httpStatusCode,totalSize,downSize){
    winform.listview.setItemText( {url;filename;statusText;fsys.formatSize(totalSize);fsys.formatSize(downSize) },id )
}

//正在下载触发
dlmgr.onReceive = function(id,sizePs,downSize){
    winform.listview.setItemText( fsys.formatSize(downSize),id,6);
    winform.listview.setItemText( fsys.formatSize(sizePs) + "/s" ,id,5);
}

//下载停止触发
dlmgr.onEnd = function(id,savepath,resumePath,contentLength){
    if( savepath ){
        winform.listview.setItemText(  "已完�?  ,id,3);
        winform.listview.setItemText( fsys.formatSize(contentLength),id,4);
    }
    else {
        winform.listview.setItemText(  "已停�?  ,id,3);
    }

    winform.listview.setItemText(  "0KB/s"  ,id,5);
    winform.listview.setItemText( "",id,6);
    //fsys.delete(resumePath)
}

//下载出错触发
dlmgr.onError = function(id,err){
    winform.listview.setItemText( err,id,3);
}

//开始下�?winform.button.oncommand = function(id,event){

    //添加下载任务非常简�?push下载参数就可以了
    //注意这里为了简化示�?任务 id 使用�?listview 控件的行�?
    //如果需要删除行则需要使用一个表保持 id 与行号的映射关系
    dlmgr.push(
        id = winform.listview.addItem( "http://ide.update.aardio.com/releases/aardio.7z" );
        url = "http://ide.update.aardio.com/releases/aardio.7z";
        filename="aardio.7z"; //文件名可以省�?        savedir = "/download/";
    )

    dlmgr.push(
        id = winform.listview.addItem( "http://wubi.aardio.com/update/wubiLex.7z" );
        url = "http://wubi.aardio.com/update/wubiLex.7z";
        savedir = "/download/"; //文件名可以省�?    )

    winform.button.disabled = true;
}

//下载任务右键管理菜单
import win.ui.menu;
winform.listview.onnotify = function(id,code,ptr){
      if( code = 0xFFFFFFFB/*_NM_RCLICK*/ ){

          var x,y = win.getMessagePos();
          var nmListView = winform.listview.getNotifyMessage(code,ptr);

          //创建弹出菜单
        var popmenu = win.ui.popmenu(winform);
        popmenu.add('取消',function(id){
            dlmgr.cancel( nmListView.iItem )
        } )
        popmenu.popup(x,y,true);
        popmenu.close();
      }
}

//关闭窗体时停止所有下�?import thread.event;
winform.onClose = function(hwnd,message,wParam,lParam){
    winform.text = "正在等待关闭";
    dlmgr.quit();
}

//显示主窗�?winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/Transfer/mtDown.md)

