[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# gdip.family 库模块帮助文�?
## gdip 成员列表

### gdip.CreateFontFamilyFromName

```aardio aardio
$.api("GdipCreateFontFamilyFromName","int(string name,ptr fontColl,pointer& fontFamily)")

```

### gdip.DeleteFontFamily

```aardio aardio
$.api("GdipDeleteFontFamily","int(PTR family)")

```

### gdip.family

字体家族�?
字体家族由具有相同字样（typeface）但字形风格（例如常规、粗体）不同的字体（font）组成�?
已安装或嵌入的字体列表（FontCollection）包含字体家族（Family），

字体家族可以用于创建不同大小、不同样式的字体(Font)

### gdip.family("字体名称")

创建字体家族�?
字体名参数必须指定不包含 Regular 这种字形风格后缀的字体名称�?
不指定字体名字时,默认�?MS Shell Dlg",

字体家族可以用于创建不同样式的同名字�?
创建失败返回空�?
### gdip.family()

[返回对象:gdipfamilyObject](#gdipfamilyObject)

### gdip.family(字体家族指针,复制对象)

字体家族指针转换为字体家族对象�?
如果参数@2为true,则复制字体家族并在对象销毁时负责回收字体家族

否则仅绑定指针到对象,这时应当谨慎使用避免字体家族指针被释�?
## gdipfamilyObject 成员列表

### gdipfamilyObject.createFont()

[返回对象:gdipfontObject](font.html#gdipfontObject)

### gdipfamilyObject.createFont(emSize,style,unit)

创建字体�?
参数@emSize指定大小,

可选参数@style 使用 \_GdipFontStyle 前缀的常量指定字形样式，默认�?\_GdipFontStyleRegular�?
可选参数@unit 指定单位,默认值为\_GdipUnitPixel

### gdipfamilyObject.delete()

释放对象�?
注意不应手工调用此函�?除非该集合内创建的字体已不再使用

### gdipfamilyObject.getName()

返回字体名�?
可选用参数@1指定语言ID，不指定时默认为 LANG\_NEUTRAL�?
语言ID设为 0x409 返回英文字体�?
### gdipfamilyObject.name

字体�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/gdip/family.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/gdip/family.md')

