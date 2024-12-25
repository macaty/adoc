[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# FlaUI.UIA3 库模块帮助文�?
## FlaUI.UIA3 成员列表

### FlaUI.UIA3.UIA3Automation

```aardio aardio
UIA3Automation

```

### FlaUI.UIA3.UIA3Automation()

创建 UIA3Automation 对象

[返回对象:FlaUIA3AutomationObject](#FlaUIA3AutomationObject)

## FlaUIA3AutomationObject 成员列表

### FlaUIA3AutomationObject.By()

[返回对象:FlaUICondition3Object](#FlaUICondition3Object)

### FlaUIA3AutomationObject.By(condition)

```aardio aardio
FlaUIA3AutomationObject.By(
    ControlType = "Edit";
    Name = "输入";/*创建节点搜索条件�?表参数@1 中每个键值对指定一个匹配条件，多个条件�?And 关系�?返回对象提供 And,Or,Not 函数�?And,Or 可以此函数创建的其他搜索条件对象作为参数*/
)

```

### FlaUIA3AutomationObject.ConditionFactory

用于创建节点搜索条件

### FlaUIA3AutomationObject.ConnectionTimeout

连接超时�?
值为 System.TimeSpan 对象�?
默认值为 2 �?
### FlaUIA3AutomationObject.FindWindow

查找窗口对象

### FlaUIA3AutomationObject.FindWindow()

[返回对象:FlaUIElementObject](#FlaUIElementObject)

### FlaUIA3AutomationObject.FindWindow(进程,窗口类名,标题,超时)

所有参数可选（至少指定一个查找条件）�?
参数@1可指�?process 对象、进程ID、EXE文件名、EXE路径�?
窗口类名、标题都支持模式匹配语法�?
超时可选指定一个单位为毫秒的数�?
### FlaUIA3AutomationObject.FocusedElement()

返回输入焦点所在节�?
[返回对象:FlaUIElementObject](#FlaUIElementObject)

### FlaUIA3AutomationObject.FromHandle()

[返回对象:FlaUIElementObject](#FlaUIElementObject)

### FlaUIA3AutomationObject.FromHwnd()

自参数@1指定的窗口句柄获取节�?
### FlaUIA3AutomationObject.FromPoint()

自参数@1指定的坐标获取节点�?
参数@1 应为 System.Drawing.Point 类型

[返回对象:FlaUIElementObject](#FlaUIElementObject)

### FlaUIA3AutomationObject.GetDesktop()

返回桌面窗口

### FlaUIA3AutomationObject.TransactionTimeout

处理超时�?
值为 System.TimeSpan 对象�?
默认值为 2 �?
## FlaUICondition3Object 成员列表

### FlaUICondition3Object.And()

逻辑与，参数 @1 可指�?By 函数返回的其他搜索条件对�?
### FlaUICondition3Object.Not()

逻辑取反

### FlaUICondition3Object.Or()

逻辑或，参数 @1 可指�?By 函数返回的其他搜索条件对�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/FlaUI/UIA3.md)

