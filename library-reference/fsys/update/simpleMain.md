[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# fsys.update.simpleMain 库模块帮助文�?
## fsys.update.simpleMain 成员列表

自动更新启动程序简化版,

更新程序与软件主程序合并到同一个程序中,

必须�?main.aardio 中调用此构造函�?

如果此函数返回true则必须退出程序，且不应显示任何其他窗�?

### fsys.update.simpleMain.checkUpdate(startUpdate)

检查更�?

参数@startUpdate指定下载新版后是否启动更新程�?

调用此函数之前必须在main.aardio中提前调用过fsys.update.simpleMain函数�?
### fsys.update.simpleMain.getReadyStatusInfo()

如果当前已下载好新版并准备更新就�?

返回statusInfo对象,包含version,description,status等属性�?
### fsys.update.simpleMain.onStatusChanged(订阅回调函数)

```aardio aardio
fsys.update.simpleMain.onStatusChanged(function(version,description,status){
    /*注意此回调可捕获到调用前或调用后的更新状态变�?/
    if(status=="ready"){
        /*新版本已下载完成，更新已准备就绪
version参数为新版本�?description为更新说�?/
    }
    elseif(status=="updated"){
        /*已更新到新版本并准备启动新版,可使用_ARGV.oldmain获得更新之前的主程序路径,_ARGV.main取得更新后主程序路径*/
    }
    elseif(status=="complete"){
        /*当前已启动新版本主程�?/
    }
    elseif(status=="latest"){
        /*当前已经是新版本*/
    }
})

```

## fsys.update 成员列表

### fsys.update.simpleMain(appName,updateUrl,downloadDir,onStatusChanged,httpHeaders,removable)

```aardio aardio
import fsys.update.simpleMain;
if( fsys.update.simpleMain(
    "/*软件产品名称*/",
    "http:",
    "/download/update-files",
    function(version,description,status){
        /*回调函数参数�?fsys.update.simpleMain.onStatusChanged 的回调函数参数相�?/;
    })){
    return 0;
}

```

## fsysUpdateSimpleStatusInfo 成员列表

### fsysUpdateSimpleStatusInfo.description

版本信息

### fsysUpdateSimpleStatusInfo.version

新版本号

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/update/simpleMain.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/update/simpleMain.md')

