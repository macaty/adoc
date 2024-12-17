[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# fsys.update.dlMgr 库模块帮助文�?
## fsys.update 成员列表

### fsys.update.dlMgr

更新/修复应用程序文件下载管理�?
### fsys.update.dlMgr()

[返回对象:fsysUpdateDlmgrObject](#fsysUpdateDlmgrObject)

### fsys.update.dlMgr(updateUrl,saveDir,appVersion,appDir)

updateUrl:版本文件version.txt的网址,也可以指定包含多个网址的数�?

更新文件存储目录

appVersion:应用程序版本�?不指定自动获取EXE产品版本

appDir:应用程序目录,不指定则为当前EXE目录

## fsysUpdateDlmgrObject 成员列表

### fsysUpdateDlmgrObject.httpHeaders

可选使用此属性指定HTTP请求�?

http头可以是web.joinHeaders支持的字符串、键值对、数组等格式

### fsysUpdateDlmgrObject.onChecksum

```aardio aardio
fsysUpdateDlmgrObject.onChecksum = function(count,total){
    io.stdout.write("已校检文件", count,'\r')
}

```

### fsysUpdateDlmgrObject.onChecksumBegin

```aardio aardio
fsysUpdateDlmgrObject.onChecksumBegin = function(total){
    io.print("开始检�?文件总数�?, total)
}

```

### fsysUpdateDlmgrObject.onConfirmDownload

```aardio aardio
fsysUpdateDlmgrObject.onConfirmDownload = function(isUpdated,appVersion,latestVersion,description){
    return !isUpdated; /*检测版本完成触发此函数,
@isUpdated参数表示是否更新,
@appVersion参数为当前版�?
@latestVersion参数为更新的版本�?
@description为更新说�?返回真继续下载更新文�?不指定此事件时默认返回@isUpdated参数*/
}

```

### fsysUpdateDlmgrObject.onDownloadBegin

```aardio aardio
fsysUpdateDlmgrObject.onDownloadBegin = function(totalSize,fileTotal){
    io.print("开始下载更新文�?, ..fsys.formatSize(totalSize),fileTotal)
}

```

### fsysUpdateDlmgrObject.onDownloadFile

```aardio aardio
fsysUpdateDlmgrObject.onDownloadFile = function(path,contentLength,fileSize){
    io.print("正在下文�?, path)
}

```

### fsysUpdateDlmgrObject.onDownloadReceive

```aardio aardio
fsysUpdateDlmgrObject.onDownloadReceive = function(sizePs,downTotalSize,fileCount){
    io.print("已下载文件数:" + fileCount, ..fsys.formatSize(downTotalSize) )
}

```

### fsysUpdateDlmgrObject.onEnd

```aardio aardio
fsysUpdateDlmgrObject.onEnd = function(updater,saveDir,appDir,mainPath,updateFilesCount){
    /*更新文件已准备就�?
以下参数中的路径已经转换为绝对路�?

updater 执行文件更新的EXE路径
saveDir 下载升级包的存储目录
appDir 需要更新的应用程序目录
mainPath 此应用程序的启动EXE路径
updateFilesCount 更新的文件数*/
}

```

### fsysUpdateDlmgrObject.onError

```aardio aardio
fsysUpdateDlmgrObject.onError = function(err,filename){
    io.print("更新遇到错误:",err,filename/*导致错误的文件路径或URL
该值可能为�?/ )
}

```

### fsysUpdateDlmgrObject.onUnCompress

```aardio aardio
fsysUpdateDlmgrObject.onUnCompress = function(fileCount,path){
    io.print("已解�?, fileCount, path)
}

```

### fsysUpdateDlmgrObject.onUnCompressBegin

```aardio aardio
fsysUpdateDlmgrObject.onUnCompressBegin = function(fileTotal){
    io.print("开始解�?文件总数�?, fileTotal)
}

```

### fsysUpdateDlmgrObject.prepareUpdate(启动下载延时)

启动「检测更�?下载文件」线程，

延时参数以毫秒为单位,为可选参�?
### fsysUpdateDlmgrObject.startUpdate

如果之前已下载新版本完成，启动自动更新，成功返回true�?
否则调用prepareUpdate函数启动「检测更�?下载文件」线�?
### fsysUpdateDlmgrObject.startUpdate(启动下载延时)

可选使用参数@1指定启动时延后下载更新文件以提升启动速度,

延时参数以毫秒为单位

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/update/dlMgr.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/update/dlMgr.md')

