[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sys.input 库模块帮助文�?
## sys.input 成员列表

系统输入法相关函数，

可用�?Win7/Win10/Win11 以及之后的系�?
相关库：win.rt.bcp47

### sys.input.?

可不用声明直接在此输入函数名并调�?input.dll �?API 函数

### sys.input.disable

禁用与启用键盘布局或输入法

可使�?win.rt.bcp47.getInputMethods 函数返回所有可用键盘布局或输入法

### sys.input.disable(layoutOrTip,enabled)

禁用与启用键盘布局或输入法�?
@layoutOrTip 使用字符串指定键盘布局或输入法�?
例如 "0409:00000409" 为英文键盘�?
@disabled 参数指定是否禁用输入法，省略参数则默认值为 true

### sys.input.find(输入法名�?

使用参数 @1 指定的输入法显示名称查找已启用的输入法信息�?
参数支持部分匹配与模式匹配�?
### sys.input.getDescription

返回键盘布局或输入法描述

### sys.input.getDescription(layoutOrTip)

返回键盘布局或输入法描述

@layoutOrTip 使用字符串指定键盘布局或输入法�?
例如 "0409:00000409" 为英文键�?
### sys.input.getEnabledLayoutOrTips()

返回一个包含所有启用的输入法或键盘布局状态的表，

键为键盘布局或输入法�?ID，例�?"0409:00000409" �?
值为如下类型之一�?
键盘布局的值为 2 \_LOTP\_KEYBOARDLAYOUT，输入法的值为 1 \_LOTP\_INPUTPROCESSOR

### sys.input.getLayoutOrTips

返回所有键盘布局与输入法的数�?
### sys.input.getLayoutOrTips(enabled,description)

返回所有键盘布局与输入法的数组�?
如果参数 @1 �?true，则不返回已禁用的元素�?
如果参数 @2 �?true，则返回数组中的每个元素都包含描述（ description ）字段�?
数组成员�?LAYOUTORTIPPROFILE 结构体，

详细用法请查看函数源码�?
一般可使用简化了�?getEnabledLayoutOrTips 函数

### sys.input.install

禁用与启用键盘布局或输入法

可使�?win.rt.bcp47.getInputMethods 函数返回所有可用键盘布局或输入法

### sys.input.install(layoutOrTip,flags)

禁用与启用键盘布局或输入法�?
@layoutOrTip 使用字符串指定键盘布局或输入法�?
例如 "0409:00000409" 为英文键盘�?
@flags 用一个数值指定选项�? 为禁用，0 为启用，

其他可用值参�?[https://docs.microsoft.com/en-us/windows/win32/tsf/installlayoutortip](https://docs.microsoft.com/en-us/windows/win32/tsf/installlayoutortip)

### sys.input.setDefault(layoutOrTip,flags)

设置默认输入法，

@layoutOrTip 使用字符串指定键盘布局或输入法�?
@flags 参数不必指定

仅支�?Win10,Win11 或之后的操作系统�?
必须提前导入库： win.rt.bcp47

系统设置每个应用窗口使用不同输入法才能实时看到效果，

可用 SystemParametersInfo 修改该设置（参�?ImTip 源码�?
### 自动完成常量

\_LOTP\_INPUTPROCESSOR=1

\_LOTP\_KEYBOARDLAYOUT=2

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/sys/input.md)

