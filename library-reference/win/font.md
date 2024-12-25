[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# win.font 库模块帮助文�?
## win.font 成员列表

### win.font.add

添加字体,

此函数加载的字体仅适用于GDI以及传统控件,

有个别控件可能不支持内存字体

建议改用 fonts.addFamily 函数可以支持GDI,GDI+,plus 控件�?
### win.font.add(字体)

添加字体,

参数@!可以是字体文件路�?资源文件路径,或内存数�?
参数2省略或为真删除成功后调用sendChange函数通知所有窗�?
返回�?为字体路径或字体句柄,返回�?为添加字体数�?失败返回空�?
注册的字体仅在当前进程可用，并可覆盖系统同名字体

### win.font.enum(proc,logfond,hdc)

```aardio aardio
win.font.enum(
    function(logfont,fullname,ftype,style,script,lpntme){
        if( ftype == 0x4/*_TRUETYPE_FONTTYPE*/ & fullname[1] != '@'#/*翻转90度字�?/ ){

        }
    },{ charset = 0x86/*_GB2312_CHARSET*/; name = "" }
)

```

### win.font.getResourceInfo("字体路径")

返回字体文件信息

注意此函数不支持内嵌资源文件

### win.font.getResourceInfo()

[返回对象:winFontResInfoObject](#winFontResInfoObject)

### win.font.remove(字体)

移除字体,参数必须是add函数的第一个非空返回�?
参数2省略或为真删除成功后调用sendChange函数通知所有窗�?
### win.font.sendChange()

字体增删后可选使用此函数通知所有顶层窗�?
## winFontResInfoObject 成员列表

### winFontResInfoObject.description

字体描述

### winFontResInfoObject.logfonts

[返回对象:logfontObject](#logfontObject)

### 自动完成常量

\_ANSI\_CHARSET=0x0

\_BALTIC\_CHARSET=0xBA

\_CHINESEBIG5\_CHARSET=0x88

\_DEFAULT\_CHARSET=0x1

\_EASTEUROPE\_CHARSET=0xEE

\_GB2312\_CHARSET=0x86

\_GREEK\_CHARSET=0xA1

\_HANGUL\_CHARSET=0x81

\_MAC\_CHARSET=0x4D

\_OEM\_CHARSET=0xFF

\_RUSSIAN\_CHARSET=0xCC

\_SHIFTJIS\_CHARSET=0x80

\_SYMBOL\_CHARSET=0x2

\_TURKISH\_CHARSET=0xA2

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/font.md)

