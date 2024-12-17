[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# string.fontRanges 库模块帮助文�?
## string.fontRanges 成员列表

用于获取字体支持的字符Unicode码列�?
### string.fontRanges.getGlyphs(fontName)

```aardio aardio
for(glyph in string.fontRanges.eachUnicodeGlyphsByName("FontAwesome") ){
    if(glyph>=0xF000) {/*glyph为字符的Unicode代码,可使用ustring.fromCharCode函数转换为字�?/}
}

```

### string.fontRanges.getRanges(hdc)

获取hdc参数中指定绘图设备正在使用的字体中所有字符的Unicode代码

### string.fontRanges.getRangesByName()

[返回对象:stringFontRangesObject](#stringFontRangesObject)

### string.fontRanges.getRangesByName(fontName)

获取fontName参数中指定字体名的字体中所有字符的Unicode代码

### string.fontRanges.getUnicodeString(fontName,first,last)

返回指定字体名支持的所有字�?

可选参数first用于指定起始Unicode代码,默认�?,

可选参数last用于指定结束Unicode代码,默认�?xFFFF

## stringFontRangesObject 成员列表

### stringFontRangesObject.findByCharCode()

参数@1指定的字符Unicode�?

如果该字符使用该字体可显示，返回该Unicode�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/string/fontRanges.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/string/fontRanges.md')

