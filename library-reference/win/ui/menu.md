[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.ui.menu 库模块帮助文�?
## win.ui.menu 成员列表

菜单支持�?
创建窗口菜单

需要先调用 import win.ui.menu，不然发布后会报错�?
开发环境下运行，为了加快启动速度，不会百分百排除所有没有引用的�?
### win.ui.menu.\_handle2menu

句柄到菜单对象映射表

### win.ui.menu.findByHandle()

[返回对象:menuObject](#menuObject)

### win.ui.menu.findByHandle(菜单句柄)

查找菜单对象

### win.ui.menu.onDrawItem

```aardio aardio
win.ui.menu.onDrawItem = function(drawItem,dpiScaleX,dpiScaleY){

    return 1;
}

```

### win.ui.menu.onMeasureItem

```aardio aardio
win.ui.menu.onMeasureItem = function(measureItem,dpiScaleX,dpiScaleY){
    measureItem.itemWidth = 80;
    measureItem.itemHeight = ::GetSystemMetrics(0xF/*_SM_CYMENU*/);
}

```

## menuObject 成员列表

### menuObject.add("标题",回调函数)

```aardio aardio
menuObject.add("菜单标题",function(){
    /*点击菜单项的回调函数�?注意添加菜单项以�?add 函数返回菜单命令ID*/

})

```

### menuObject.add("标题",子菜�?

添加子菜�?
返回添加的子菜单

### menuObject.add()

添加分隔�?
### menuObject.add(参数�?

```aardio aardio
menuObject.add(
    text = "标题";
    bitmap = "位图句柄或路径、或图像数据,可选参�?;
    bitmapCheckd = "选中位图句柄或路径、或图像数据,可选参�?;
    proc = function(id){
        /*点击菜单项的回调函数�?注意添加菜单项以�?add 函数返回菜单命令ID*/
    };
    id = 可选参�?
    flag = 可选参�?
);

```

### menuObject.addTable

```aardio aardio
menuObject.addTable( {
    { "菜单文本";  function(id){
        /*菜单事件回调函数*/
    } }; { /*分隔�?/ }
    { "退出程�?; function(id){
        winform.close()
    } };
} )

```

### menuObject.check

勾选或取消勾选菜单项

### menuObject.check(菜单项命令ID,是否选中,0/\*\_MF\_BYCOMMAND\*/)

勾选或取消勾选菜单项，参数@2默认�?true�?
如果参数@3�?/\*\_MF\_BYCOMMAND\*/则参数@1为菜单命令ID

### menuObject.check(菜单项序�?是否选中)

勾选或取消勾选菜单项，参数@2默认�?true

### menuObject.checked

返回菜单项是否选中状�?
### menuObject.checked(菜单项命令ID,0/\*\_MF\_BYCOMMAND\*/)

返回菜单项是否选中状态e�?
如果参数@2�?/\*\_MF\_BYCOMMAND\*/则参数@1为菜单命令ID

### menuObject.checked(菜单项序�?

返回菜单项是否选中状�?
### menuObject.click(菜单项命令ID,0/\*\_MF\_BYCOMMAND\*/)

模拟点击指定命令ID的菜单项

### menuObject.click(菜单项序�?

模拟点击指定位置菜单�?
### menuObject.close()

关闭菜单

### menuObject.count()

返回菜单子项数目

### menuObject.delete

删除指定位置菜单�?
### menuObject.delete(菜单项命令ID,0/\*\_MF\_BYCOMMAND\*/)

移除指定命令ID的菜单项

被移除的如果是子菜单则销�?不可重用

### menuObject.delete(菜单项序�?

删除指定位置菜单�?
被移除的如果是子菜单则销�?不可重用

### menuObject.enable

启用或禁用菜单项

### menuObject.enable(菜单项命令ID,是否启用,0/\*\_MF\_BYCOMMAND\*/)

启用或禁用菜单项，参数@2默认�?true�?
如果参数@3�?/\*\_MF\_BYCOMMAND\*/则参数@1为菜单命令ID

### menuObject.enable(菜单项序�?是否启用)

启用或禁用菜单项，参数@2默认�?true

### menuObject.getId

根据指定位置序号返回菜单项的命令ID

### menuObject.getId(菜单项序�?

根据指定位置序号返回菜单项的命令ID

### menuObject.getPos

根据菜单项的命令ID返回菜单位置序号

### menuObject.getPos(菜单项命令I)

根据菜单项的命令ID返回菜单位置序号

### menuObject.getString

返回菜单项文�?
### menuObject.getString(菜单项命令ID,0/\*\_MF\_BYCOMMAND\*/)

返回菜单项文本，

如果参数@2�?/\*\_MF\_BYCOMMAND\*/则参数@1为菜单命令ID

### menuObject.getString(菜单项序�?

返回菜单项文�?
### menuObject.handle

菜单句柄

### menuObject.insert( 1 )

在指定位置插入分隔线

### menuObject.insert(位置,标题,回调函数)

```aardio aardio
menuObject.insert(1,"菜单标题",function(){
    /*点击菜单项的回调函数�?注意添加菜单项以�?insert 函数返回菜单命令ID*/

})

```

### menuObject.insert(参数�?

```aardio aardio
menuObject.insert(
    position = 1;
    text = "标题";
    bitmap = "位图句柄或路径、或图像数据,可选参�?;
    bitmapCheckd = "选中位图句柄或路径、或图像数据,可选参�?;
    proc = function(id){
        /*点击菜单项的回调函数�?注意添加菜单项以�?add 函数返回菜单命令ID*/
    };
    id = 可选参�?
    flag = 可选参�?
);

```

### menuObject.onMenuItemClick

```aardio aardio
menuObject.onMenuItemClick = function(id){
    menuFile.selId = id;/*指定默认菜单回调函数*/
}

```

### menuObject.ownerDraw

启用自绘

系统菜单自绘没多大意�?建议使用弹出窗口模拟菜单即可

### menuObject.redraw()

重绘菜单

### menuObject.remove

移除指定位置菜单�?
### menuObject.remove(菜单项命令ID,0/\*\_MF\_BYCOMMAND\*/)

移除指定命令ID的菜单项

被移除的如果是子菜单并不销�?可重�?
### menuObject.remove(菜单项序�?

移除指定位置菜单�?
被移除的如果是子菜单并不销�?可重�?
### menuObject.reset

重设菜单回调函数

### menuObject.reset(新的回调函数,菜单ID,0/\*\_MF\_BYCOMMAND\*/)

重设菜单回调函数

### menuObject.reset(新的回调函数,菜单位置)

重设菜单回调函数

### menuObject.selId

获取或修改当前选中项命令ID,单选模�?
### menuObject.selIndex

获取或修改当前选中项索�?单选模�?
### menuObject.selText

获取或修改当前选中项文�?单选模�?
### menuObject.setBitmap

设置菜单项位�?
### menuObject.setBitmap(菜单项命令ID,位图,选中位图,0/\*\_MF\_BYCOMMAND\*/)

设置菜单项位�?

选中位图为可选参�?

图像可以是句柄指�?也可以是图像文件路径或数据，

如果参数@4�?/\*\_MF\_BYCOMMAND\*/则参数@1为菜单命令ID

### menuObject.setBitmap(菜单项序�?位图,选中位图)

设置菜单项位�?

选中位图为可选参�?

图像可以是句柄指�?也可以是图像文件路径或数�?
### menuObject.setString

设置菜单项文�?
### menuObject.setString(菜单项命令ID,字符�?0/\*\_MF\_BYCOMMAND\*/)

设置菜单项文本，

如果参数@3�?/\*\_MF\_BYCOMMAND\*/则参数@1为菜单命令ID

### menuObject.setString(菜单项序�?字符�?

设置菜单项文�?
### menuObject.subMenu()

[返回对象:popmenuObject](#popmenuObject)

### menuObject.subMenu(1)

返回指定位置子菜�?
## popmenuObject 成员列表

### popmenuObject.add("标题",回调函数)

```aardio aardio
popmenuObject.add("菜单标题",function(){
    /*点击菜单项的回调函数�?注意添加菜单项以�?add 函数返回菜单命令ID*/

})

```

### popmenuObject.add("标题",子菜�?

添加子菜�?
返回添加的子菜单

### popmenuObject.add()

添加分隔�?
### popmenuObject.add(参数�?

```aardio aardio
popmenuObject.add(
    text = "标题";
    bitmap = "位图句柄或路径、或图像数据,可选参�?;
    bitmapCheckd = "选中位图句柄或路径、或图像数据,可选参�?;
    proc = function(id){
        /*点击菜单项的回调函数�?注意添加菜单项以�?add 函数返回菜单命令ID*/
    };
    id = 可选参�?
    flag = 可选参�?
);

```

### popmenuObject.addTable

```aardio aardio
popmenuObject.addTable( {
    { "菜单文本";  function(id){
        /*菜单事件回调函数*/
    } }; { /*分隔�?/ }
    { "退出程�?; function(id){
        winform.close()
    } };
} )

```

### popmenuObject.check

勾选或取消勾选菜单项

### popmenuObject.check(菜单项命令ID,是否选中,0/\*\_MF\_BYCOMMAND\*/)

勾选或取消勾选菜单项，参数@2默认�?true�?
如果参数@3�?/\*\_MF\_BYCOMMAND\*/则参数@1为菜单命令ID

### popmenuObject.check(菜单项序�?是否选中)

勾选或取消勾选菜单项，参数@2默认�?true

### popmenuObject.checked

返回菜单项是否选中状�?
### popmenuObject.checked(菜单项命令ID,0/\*\_MF\_BYCOMMAND\*/)

返回菜单项是否选中状态e�?
如果参数@2�?/\*\_MF\_BYCOMMAND\*/则参数@1为菜单命令ID

### popmenuObject.checked(菜单项序�?

返回菜单项是否选中状�?
### popmenuObject.click(菜单项命令ID,0/\*\_MF\_BYCOMMAND\*/)

模拟点击指定命令ID的菜单项

### popmenuObject.click(菜单项序�?

模拟点击指定位置菜单�?
### popmenuObject.close()

关闭菜单

### popmenuObject.count()

返回菜单子项数目

### popmenuObject.delete

删除指定位置菜单�?
### popmenuObject.delete(菜单项命令ID,0/\*\_MF\_BYCOMMAND\*/)

移除指定命令ID的菜单项

被移除的如果是子菜单则销�?不可重用

### popmenuObject.delete(菜单项序�?

删除指定位置菜单�?
被移除的如果是子菜单则销�?不可重用

### popmenuObject.enable

启用或禁用菜单项

### popmenuObject.enable(菜单项命令ID,是否启用,0/\*\_MF\_BYCOMMAND\*/)

启用或禁用菜单项，参数@2默认�?true�?
如果参数@3�?/\*\_MF\_BYCOMMAND\*/则参数@1为菜单命令ID

### popmenuObject.enable(菜单项序�?是否启用)

启用或禁用菜单项，参数@2默认�?true

### popmenuObject.fireId(id,hwnd)

调用菜单回调函数

可选指定接收命令的窗体句柄

可添加任意个附加参数

### popmenuObject.getId

根据指定位置序号返回菜单项的命令ID

### popmenuObject.getId(菜单项序�?

根据指定位置序号返回菜单项的命令ID

### popmenuObject.getPos

根据菜单项的命令ID返回菜单位置序号

### popmenuObject.getPos(菜单项命令I)

根据菜单项的命令ID返回菜单位置序号

### popmenuObject.getString

返回菜单项文�?
### popmenuObject.getString(菜单项命令ID,0/\*\_MF\_BYCOMMAND\*/)

返回菜单项文本，

如果参数@2�?/\*\_MF\_BYCOMMAND\*/则参数@1为菜单命令ID

### popmenuObject.getString(菜单项序�?

返回菜单项文�?
### popmenuObject.handle

菜单句柄

### popmenuObject.insert( 1 )

在指定位置插入分隔线

### popmenuObject.insert(位置,标题,回调函数)

```aardio aardio
popmenuObject.insert(1,"菜单标题",function(){
    /*点击菜单项的回调函数�?注意添加菜单项以�?insert 函数返回菜单命令ID*/

})

```

### popmenuObject.insert(参数�?

```aardio aardio
popmenuObject.insert(
    position = 1;
    text = "标题";
    bitmap = "位图句柄或路径、或图像数据,可选参�?;
    bitmapCheckd = "选中位图句柄或路径、或图像数据,可选参�?;
    proc = function(id){
        /*点击菜单项的回调函数�?注意添加菜单项以�?add 函数返回菜单命令ID*/
    };
    id = 可选参�?
    flag = 可选参�?
);

```

### popmenuObject.onMenuItemClick

```aardio aardio
popmenuObject.onMenuItemClick = function(id){
    menuFile.selId = id;/*指定默认菜单回调函数*/
}

```

### popmenuObject.ownerDraw

启用自绘

系统菜单自绘没多大意�?建议使用弹出窗口模拟菜单即可

### popmenuObject.popId

弹出菜单并返回用户点选ID

### popmenuObject.popId(x坐标,y坐标,是否屏幕坐标,选项)

弹出菜单

并返回用户点选ID

未选择或发生错误则返回�?

如果不指定坐�?则自动获取鼠标当前位�?

可选用参数@4指定 _TPM_ 前缀的选项,

例如 \_TPM\_BOTTOMALIGN 指定坐标 y 指定菜单底部位置

### popmenuObject.popup

弹出菜单

### popmenuObject.popup(x坐标,y坐标,是否屏幕坐标,选项)

弹出菜单

如果不指定坐�?则自动获取鼠标当前位�?

可选用参数@4指定 _TPM_ 前缀的选项,

例如 \_TPM\_BOTTOMALIGN 指定坐标 y 指定菜单底部位置

### popmenuObject.remove

移除指定位置菜单�?
### popmenuObject.remove(菜单项命令ID,0/\*\_MF\_BYCOMMAND\*/)

移除指定命令ID的菜单项

被移除的如果是子菜单并不销�?可重�?
### popmenuObject.remove(菜单项序�?

移除指定位置菜单�?
被移除的如果是子菜单并不销�?可重�?
### popmenuObject.reset

重设菜单回调函数

### popmenuObject.reset(新的回调函数,菜单ID,0/\*\_MF\_BYCOMMAND\*/)

重设菜单回调函数

### popmenuObject.reset(新的回调函数,菜单位置)

重设菜单回调函数

### popmenuObject.selId

获取或修改当前选中项命令ID,单选模�?
### popmenuObject.selIndex

获取或修改当前选中项索�?单选模�?
### popmenuObject.selText

获取或修改当前选中项文�?单选模�?
### popmenuObject.setBitmap

设置菜单项位�?
### popmenuObject.setBitmap(菜单项命令ID,位图,选中位图,0/\*\_MF\_BYCOMMAND\*/)

设置菜单项位�?

选中位图为可选参�?

图像可以是句柄指�?也可以是图像文件路径或数据，

如果参数@4�?/\*\_MF\_BYCOMMAND\*/则参数@1为菜单命令ID

### popmenuObject.setBitmap(菜单项序�?位图,选中位图)

设置菜单项位�?

选中位图为可选参�?

图像可以是句柄指�?也可以是图像文件路径或数�?
### popmenuObject.setString

设置菜单项文�?
### popmenuObject.setString(菜单项命令ID,字符�?0/\*\_MF\_BYCOMMAND\*/)

设置菜单项文本，

如果参数@3�?/\*\_MF\_BYCOMMAND\*/则参数@1为菜单命令ID

### popmenuObject.setString(菜单项序�?字符�?

设置菜单项文�?
### popmenuObject.subMenu()

[返回对象:popmenuObject](#popmenuObject)

### popmenuObject.subMenu(1)

返回指定位置子菜�?
## win.ui 成员列表

### win.ui.getMenu()

[返回对象:menuObject](#menuObject)

### win.ui.getMenu(hwnd)

返回窗口菜单

参数@1可指定窗体对象或窗体句柄

返回的菜单对象不能添加菜�?
### win.ui.getSysMenu()

[返回对象:popmenuObject](#popmenuObject)

### win.ui.getSysMenu(winform)

返回系统菜单

参数@1可指定窗体对象或窗体句柄

请事先导入win.ui.menu

### win.ui.getSysMenu(winform,true)

返回系统菜单

并重置为缺省状�?
参数@1可指定窗体对象或窗体句柄

请事先导入win.ui.menu

### win.ui.menu()

[返回对象:menuObject](#menuObject)

[返回对象:menuObject](#menuObject)

### win.ui.menu(窗口)

创建窗口菜单

参数 @1 可指定窗口或控件对象�?
如果参数 @1 指定控件对象则自动转换为所在的父窗口对象�?
如果参数 @1 传入窗口句柄，则添加菜单项无�?
### win.ui.menu(窗口,菜单句柄)

使用存在的菜单句柄创建菜单对象，

如果参数 @1 指定控件对象则自动转换为所在的父窗口对象�?
如果参数 @1 传入窗口句柄，则添加菜单项无�?
### win.ui.popmenu

创建弹出菜单

需要先调用 import win.ui.menu，不然发布后会报错�?
开发环境下运行，为了加快启动速度，不会百分百排除所有没有引用的�?
### win.ui.popmenu()

[返回对象:popmenuObject](#popmenuObject)

### win.ui.popmenu(窗口)

创建弹出菜单�?
如果参数 @1 指定控件对象则自动转换为所在的父窗口对象�?
如果参数 @1 传入窗口句柄，则添加菜单项无�?
### win.ui.popmenu(窗口,菜单句柄)

使用存在的菜单句柄创建弹出菜单对象，

如果参数 @1 指定控件对象则自动转换为所在的父窗口对象�?
如果参数 @1 传入窗口句柄，则添加菜单项无�?
### 自动完成常量

\_MENU\_ITEM\_IS\_SUBMENU=-1

\_TPM\_BOTTOMALIGN=0x20

\_TPM\_CENTERALIGN=0x4

\_TPM\_LEFTALIGN=0

\_TPM\_RIGHTALIGN=0x8

\_TPM\_TOPALIGN=0

\_TPM\_VCENTERALIGN=0x10

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/menu.md)

