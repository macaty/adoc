[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 精简字体

```aardio aardio
import console;
import py3;

//精简 FontAwesome 字体需要保留的字符，生成新�?fonts.fontAwesomeSub �?var fontAwesomeSub = '\uF254\uF251\uF252\uF253\uF250\uE8CE\uF0F6\uF007\uF0C8\uF14a\uF019\uF0E2\uF0E2\uF013\uF014\uF0AA\uF067\uF1F8\uF044';

//导入 Python 模块 fontTools.ttLib
var ttLib = py3.import("fontTools.ttLib");
if(!ttLib){
    import py3.pip;
    py3.pip.setIndexUrl("aliyun");
    py3.pip("install","fonttools");

    ttLib = py3.import("fontTools.ttLib");
}

//精简 TTF 字体文件
var subsetFont = function(srcPath, dstPath, text){
    var font = ttLib.TTFont(io.fullpath(srcPath));

    //拆分为字符数�?    var textArray = string.split(text);

    //转换�?Python 集合对象
    pySetUnicodes = py3.builtin.set( unicodes )

    //创建子集
    var subsetter = py3.import("fontTools.subset").Subsetter();
    subsetter.$populate( text = text );

    //字体子集�?    subsetter.subset(font);

    //保存精简后的字体
    font.save(io.fullpath(dstPath));
}

import ide;
var projDir = ide.getProjectDir();
if(!#projDir){
    error("请先打开工程文件");
}

//生成导入精简字体�?aardio 库文�?var code = /*****
import fsys;
import fonts;

namespace fonts.fontAwesomeSub{

    family = ..fonts.addFamily($"/lib/fonts/.res/fontAwesomeSub.ttf","FontAwesome")
}

/**intellisense()
fonts.fontAwesomeSub = 导入FontAwesome 图标字体用于支持GDI/GDI+，控�?plus控件�?\n所有图标请参考aardio工具->文本文件->图标字体
fonts.fontAwesomeSub.family = GDI+字体家族,可用于plus控件,gdip等库函数,\n!gdipfamily.
end intellisense**/
*****/
string.save(io.joinpath(projDir,"/lib/fonts/fontAwesomeSub.aardio"),code);

var outPath = io.joinpath(projDir,"\lib\fonts\.res\fontAwesomeSub.ttf");
if(io.exist(outPath)){
    io.remove(outPath);
    if(io.exist(outPath)){
        error("请先退�?aardio 并删除字体文件："+outPath);
    }
}

//精简字体
subsetFont(
    "~\lib\fonts\.res\FontAwesome.ttf", //原字体路�?
    outPath, //输出路径
    fontAwesomeSub,
);

console.log("已输出精简字体�?,outPath)
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/fontTools.md)

