[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 多字节字�?
```aardio aardio
//多字节字�?import console;

var str = /**
取出所有的中文字符
在模式匹配中,圆点'.'表示任意单字节字�?而冒�?:'表示任意多字节字�?例如中文)
abcddddddddddddd这是一个中文字符串adfasdfasdf这又是一个中文字符串<a href="">这是超链接标�?/a>字符�?*/

for str in string.gmatch(str,':+') {
   console.log(str)
}
console.more(1);

console.log("取左�?个汉�?,string.left(str,3,true) );
console.log("取右�?个汉�?,string.right(str,3,true) );
console.log("取第2到第5个汉�?,string.slice(str,2,5,true) );
console.more(1);

//将中文字符串转换为数�?var tab = string.split(str )
for(i=1;#tab;1){
    console.log( tab[i] ) //显示第i个字�?}
console.more(1)

//转换为Uniocde( UTF-16 )
var ustring = string.toUtf16(str);
for(i=1;#ustring / 2 ;1){ //UTF-16每个字符串固定为两个字节
    console.log( ustring[i],ustring[[i]] ) //下标操作符可以方便的支持Unicode双字�?}

//转换为拼�?import string.conv.pinyin;
console.log( string.conv.pinyin("新年�?) )
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Text/wchar.md)

