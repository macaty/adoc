[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# gdip.stringformat 库模块帮助文�?
## gdip 成员列表

### gdip.CloneStringFormat

```aardio aardio
$.api("GdipCloneStringFormat","int(PTR strFmt,int& newFormat)")

```

### gdip.CreateStringFormat

```aardio aardio
$.api("GdipCreateStringFormat","int(int formatAttributes,word language,pointer& StringFormat)")

```

### gdip.DeleteStringFormat

```aardio aardio
$.api("GdipDeleteStringFormat","int(PTR strFmt)")

```

### gdip.GetStringFormatAlign

```aardio aardio
$.api("GdipGetStringFormatAlign","int(PTR strFmt,int& align)")

```

### gdip.GetStringFormatFlags

```aardio aardio
$.api("GdipGetStringFormatFlags","int(PTR strFmt,int& flags)")

```

### gdip.GetStringFormatHotkeyPrefix

```aardio aardio
$.api("GdipGetStringFormatHotkeyPrefix","int(PTR strFmt,int& hkPrefix)")

```

### gdip.GetStringFormatLineAlign

```aardio aardio
$.api("GdipGetStringFormatLineAlign","int(PTR strFmt,int& align)")

```

### gdip.GetStringFormatTrimming

```aardio aardio
$.api("GdipGetStringFormatTrimming","int(PTR strFmt,int& trimming)")

```

### gdip.SetStringFormatAlign

```aardio aardio
$.api("GdipSetStringFormatAlign","int(PTR strFmt,int align)")

```

### gdip.SetStringFormatFlags

```aardio aardio
$.api("GdipSetStringFormatFlags","int(PTR strFmt,int flags)")

```

### gdip.SetStringFormatHotkeyPrefix

```aardio aardio
$.api("GdipSetStringFormatHotkeyPrefix","int(PTR strFmt,int hkPrefix)")

```

### gdip.SetStringFormatLineAlign

```aardio aardio
$.api("GdipSetStringFormatLineAlign","int(PTR strFmt,int align)")

```

### gdip.SetStringFormatTrimming

```aardio aardio
$.api("GdipSetStringFormatTrimming","int(PTR strFmt,int trimming)")

```

### gdip.stringformat()

[返回对象:gdipstringformatObject](#gdipstringformatObject)

### gdip.stringformat(formatAttributes,language)

创建文本格式对象

参数都是可选参�?默认值为0

## gdip.stringformat 成员列表

### gdip.stringformat.genericTypographic()

返回一个格式对�?
测量字符串的长度时，禁止GDI+添加额外长度或宽�?
测量结果偏小

[返回对象:gdipstringformatObject](#gdipstringformatObject)

## gdipstringformatObject 成员列表

### gdipstringformatObject.align

```aardio aardio
gdipstringformatObject.align = _GdipStringAlignment ;

```

### gdipstringformatObject.delete()

删除对象

### gdipstringformatObject.flags

```aardio aardio
gdipstringformatObject.flags = _GdipStringFormatFlags ;

```

### gdipstringformatObject.hotkeyPrefix

```aardio aardio
gdipstringformatObject.hotkeyPrefix = _GdipHotkeyPrefix ;

```

### gdipstringformatObject.lineAlign

```aardio aardio
gdipstringformatObject.lineAlign = _GdipStringAlignment ;

```

### gdipstringformatObject.trimming

```aardio aardio
gdipstringformatObject.trimming = _GdipStringTrimming ;

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/gdip/stringformat.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/gdip/stringformat.md')

