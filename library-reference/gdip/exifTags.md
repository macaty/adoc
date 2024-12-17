[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# gdip.exifTags 库模块帮助文�?
## gdip 成员列表

### gdip.exifTags

Exif 标签列表

此名字空间存储的�?Exif �?ID 时对应的值为标签名称�?
键为标签名称时对应的值为数值类型的 ID�?
创建 Exif 对象�?
### gdip.exifTags()

[返回对象:gdpExifTagsObject](#gdpExifTagsObject)

### gdip.exifTags(imageOrBitmap)

创建 Exif 对象�?
参数 @1 可指�?gdip.image �?gdip.bitmap 对象�?
### gdip.exifTags(imagePathOrBuffer)

创建 Exif 对象�?
参数 @1 可指定图像路径中内存数据�?
## gdpExifTagsObject 成员列表

### gdpExifTagsObject.each()

```aardio aardio
for( tagId,tagName,propertyItem in gdpExifTagsObject.each() ){
     propertyItem./*遍历图像 Exif 属�?/
}

[返回对象:gdipExifItemObject](#gdipExifItemObject)

```

### gdpExifTagsObject.getById()

读取 Exif 属性，参数 @1 指定标签 ID�?
[返回对象:gdipExifItemObject](#gdipExifItemObject)

### gdpExifTagsObject.getByName()

读取 Exif 属性，参数 @1 指定标签名称�?
[返回对象:gdipExifItemObject](#gdipExifItemObject)

### gdpExifTagsObject.image

当前加载�?gdip.image 对象�?
[返回对象:gdipimageObject](image.html#gdipimageObject)

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/gdip/exifTags.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/gdip/exifTags.md')

