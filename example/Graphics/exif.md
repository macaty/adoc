[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 图像 Exif 信息

```aardio aardio
//图像 Exif 信息
import console.int;
import fsys.dlg;
var jpgPath = fsys.dlg.open("JPG 图像文件|*.jpg||","请选择图像",io.getSpecial(0x27 /*_CSIDL_MYPICTURES*/) )
if(!jpgPath) return;

import gdip.exifTags;
var exifTags = gdip.exifTags(jpgPath);

/*
gdip.bitmap,gdip.image 都提供读�?Exif 属性的功能�?exifTags 只是简单封装了 gdip.image �? eachProperty 等函数�?*/
for( tagId,tagName,propertyItem,t in exifTags.each() ){
    var tagName = gdip.exifTags[tagId]:"Unknown";

    /*
    propertyItem 是一个结构体（struct）�?    其中 type 字段是一个数值表示的数据类型，所有类型参�?gdip.image.convertPropertyValue 源码�?    �?value 字段记录了原始的属性值，这是一个原生数组�?    数值类型存�?number 字段，一般是 value.array[1] 的数值格式�?    text 字段用于表示字符串值，经纬度的 text 字段为度分秒或度分格式�?    支持�?tostring 转为文本，或�?tonumber 转为单个数值�?    */

    //if(string.startWith(tagName,"Gps")){
        console.printf('0x%04x\t%s\t%s',tagId, tagName, tostring(propertyItem)  )
        console.more( 10 )
    //}
}

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Graphics/exif.md)

