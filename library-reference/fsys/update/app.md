[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# fsys.update.app 库模块帮助文�?
## fsys.update 成员列表

### fsys.update.app

执行更新程序

### fsys.update.app()

[返回对象:fsysUpdateAppObject](#fsysUpdateAppObject)

### fsys.update.app(更新�?目标目录,是否保留更新补丁,是否允许移除文件)

创建更新程序,

如果参数@3为true，则更新后不删除源补�?
如果参数@4指定为false，则更新时不删除在新版补丁中已移除的旧版本文件�?
## fsysUpdateAppObject 成员列表

### fsysUpdateAppObject.apply()

创建更新线程,安装更新

### fsysUpdateAppObject.onCopyBegin

```aardio aardio
fsysUpdateAppObject.onCopyBegin = function(total){
     /*开始复制文�?/
}

```

### fsysUpdateAppObject.onCopyFailed

```aardio aardio
fsysUpdateAppObject.onCopyFailed = function(path){
     /*文件被占�?返回false取消更新*/
}

```

### fsysUpdateAppObject.onCopyFile

```aardio aardio
fsysUpdateAppObject.onCopyFile = function(path,count){
     /*开始复制参数@1指定的文�?返回false取消更新*/
}

```

### fsysUpdateAppObject.onEnd

```aardio aardio
fsysUpdateAppObject.onEnd = function(succeeded){
     /*更新操作已全部完�?/
}

```

### fsysUpdateAppObject.onError

```aardio aardio
fsysUpdateAppObject.onError = function(err,filename){
    io.print("更新遇到错误:",err,filename/*导致错误的文件路径或URL
该值可能为�?/ )
}

```

### fsysUpdateAppObject.onProcessCheck

```aardio aardio
fsysUpdateAppObject.onProcessCheck = function(paths){
     /*参数是更新程序所在目录下已运行的进程路径,
返回false取消更新*/
}

```

### fsysUpdateAppObject.onProcessFailed

```aardio aardio
fsysUpdateAppObject.onProcessFailed = function(paths){
     /*更新程序需要退出进�?
参数是程序启动路径数�?返回false取消更新*/
}

```

### fsysUpdateAppObject.updateInfo.description

更新说明

### fsysUpdateAppObject.updateInfo.version

更新的软件版本号

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/update/app.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/update/app.md')

