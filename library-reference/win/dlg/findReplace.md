[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.dlg.findReplace 库模块帮助文�?
## win.dlg 成员列表

### win.dlg.findReplace

查找替换对话�?
### win.dlg.findReplace()

创建查找替换对话�?
参数中指定父窗口对象,注意不能仅指定父窗口句柄�?
一个父窗口上不要创建多个查找对话框

[返回对象:windlgfindReplaceObject](#windlgfindReplaceObject)

## windlgfindReplaceObject 成员列表

### windlgfindReplaceObject.close()

关闭对话�?
### windlgfindReplaceObject.find()

打开查找文本对话�?
可选在参数中指定findWhat属性为空时的默认查找文�?
### windlgfindReplaceObject.findWhat

要查找的文本

用户输入过的查找文本会放在这�?

下次打开对话框作为默认查找字符串

### windlgfindReplaceObject.flags

查找替换选项,

此属性可以作为richedit的findText,replaceText函数参数使用

### windlgfindReplaceObject.onReplace

```aardio aardio
windlgfindReplaceObject.onReplace = function(findWhat,replaceWith,down,matchCase,wholeWord){
    /*替换触发此事�?参数�?findWhat 正在查找的字符串
replaceWith 替换字符�?down 是否向下查找
matchCase 是否区分大小�?wholeWord 是否全字匹配*/
}

```

### windlgfindReplaceObject.onReplaceAll

```aardio aardio
windlgfindReplaceObject.onReplaceAll = function(findWhat,replaceWith,down,matchCase,wholeWord){
    /*全部替换触发此事�?参数�?findWhat 查找字符�?replaceWith 替换字符�?down 是否向下查找
matchCase 是否区分大小�?wholeWord 是否全字匹配*/
}

```

### windlgfindReplaceObject.onSearch

```aardio aardio
windlgfindReplaceObject.onSearch = function(findWhat,down,matchCase,wholeWord){
    /*查找触发此事�?参数�?findWhat 正在查找的字符串
down 是否向下查找
matchCase 是否区分大小�?wholeWord 是否全字匹配*/
}

```

### windlgfindReplaceObject.replace()

打开替换文本对话�?
可选在参数中指定findWhat属性为空时的默认查找文�?
### windlgfindReplaceObject.replaceWith

要替换的文本

用户输入过的替换文本会放在这�?

下次打开对话框作为默认替换字符串

### windlgfindReplaceObject.show(false)

隐藏对话�?
### windlgfindReplaceObject.title

窗口标题,需要在首次打开对话框以前设�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/dlg/findReplace.md)

