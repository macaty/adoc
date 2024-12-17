[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.ui.explorer 库模块帮助文�?
## win.ui 成员列表

### win.ui.explorer

用于创建类似资源管理器的文件树形视图

### win.ui.explorer()

创建类似资源管理器的文件树形视图�?
请在参数中指定一个已创建�?treeview 视图对象�?
创建对象时会自动启用 treeview 控件的滚动条�?
默认会在树形视图控件顶部自动搜索下拉框用于显示驱动器列表�?
[返回对象:winUiExplorerObject](#winUiExplorerObject)

## winUiExplorerObject 成员列表

### winUiExplorerObject.combobox

用于显示驱动器的下拉�?

默认会在树形视图控件顶部自动搜索下拉�?也可以自行指�?
[返回对象:comboboxObject](#comboboxObject)

### winUiExplorerObject.getCurrentFilePath()

返回当前选中节点文件路径

注意onClick事件触发时树形控件尚未更改选中状�?
### winUiExplorerObject.getFilePath(hItem)

返回节点文件路径,不指定节点句柄时返回根路�?
### winUiExplorerObject.insertDir(name,path,hItemParent)

插入目录节点�?
参数 @name 指定显示名称�?
参数 @path 指定节点绑定的目录路径�?
可选用 @hItemParent 指定父节点句�?不指�?@hItem 时添加到根节�?
### winUiExplorerObject.insertFile(name,path,hItemParent)

插入文件节点�?
参数 @name 指定显示名称�?
参数 @path 指定节点绑定的文件路径�?
可选用 @hItemParent 指定父节点句�?不指�?@hItem 时添加到根节�?
### winUiExplorerObject.insertItem(filename,hItemParent)

添加文件名或目录名到指定节点�?
可选用 @hItemParent 指定父节点句�?不指�?@hItem 时添加到根节�?
### winUiExplorerObject.loadFile

搜索文件并加载到树形视图

### winUiExplorerObject.loadFile("目录路径","通配�?,"模式匹配")

搜索文件并加载到树形视图

不指定任何参数调用此函数时默认显示所有硬盘分�?

除参数@1以外,其他参数可�?
参数@2使用模式匹配语法匹配文件�?
通配符默认值是"\*.\*",也可以传入通配符数�?
### winUiExplorerObject.onClick

```aardio aardio
winUiExplorerObject.onClick = function(filePath,hItem){
    /*用户单击节点或节点图�?此时尚未改变选中节点*/
}

```

### winUiExplorerObject.onDoubleClick

```aardio aardio
winUiExplorerObject.onDoubleClick = function(filePath,hItem){
    /*用户双击节点或节点图�?此时尚未改变选中节点*/
}

```

### winUiExplorerObject.onExpandedOnce

```aardio aardio
winUiExplorerObject.onExpandedOnce = function(hItem){
    /*第一次展开参数指定的节�?/
}

```

### winUiExplorerObject.onRightClick

```aardio aardio
winUiExplorerObject.onRightClick = function(filePath,hItem,x,y){
    /*用户右键单击节点*/
}

```

### winUiExplorerObject.onSelChanged

```aardio aardio
winUiExplorerObject.onSelChanged = function(filePath,hItem){
    /*用户已改变选中节点*/
}

```

### winUiExplorerObject.pattern

用于匹配要显示的文件或目录名的模式串

### winUiExplorerObject.reloadFile

重新加载指定目录下的文件

### winUiExplorerObject.reloadFile("目录路径",节点句柄)

重新加载指定目录下的文件到参数@2指定的节�?

参数@2如果省略则刷新所有节�?
### winUiExplorerObject.rootPath

文件视图根目录路�?
### winUiExplorerObject.setIconSize("large")

显示大图�?
可选参数有：large,small,extralarge,syssmall,jumbo

### winUiExplorerObject.setItemText(hItem,text)

设置节点显示文本�?
参数 @hItem 指定树视图节点句柄�?
参数 @text 指定要显示的文本�?
### winUiExplorerObject.translatePath

function(dirPath,files,dirs){
\_\_/\*转换显示名称�?
dirPath 为当前目录路径�?
files,dirs �?fsys.list 返回的文件名与子目录数组�?
数组同时包含显示名称与实际路径对照的名值对�?
必须返回相同结构�?files,dirs。\*/
return files,dirs;
}

### winUiExplorerObject.wildcard

用于匹配要显示的文件名通配�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/explorer.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/explorer.md')

