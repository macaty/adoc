[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 模式匹配

```aardio aardio
//模式匹配
import console;

/*
《模匹匹配快速入门�?https://www.aardio.com/zh-cn/doc/guide/language/pattern-matching.html

《模匹匹配语法�?https://www.aardio.com/zh-cn/doc/library-guide/builtin/string/patterns.html
*/

//查找字符串位�?var i,j = string.find("abc456d" ,"c\d+");

if( i ) {
   console.log("�?'abc456d' 中找�?c\d+" ,"�? + i + "�? + j);
}

//匹配字符串：圆括号添加匹配分�?—�?并增加返回�?var a,b = string.match("abc456d" ,"(c(\d+))");
console.log(a,b);

//替换字符串：在模式匹配中 .圆点标记匹配任意字符
str = string.replace("abcd",".","k");
console.log(str); //输出kkkk

str = string.replace("abcd",".","k",1);
console.log(str); //输出kbcd

var url = console.getText( "请输入网址:" )

import inet.url;
console.log("直接用标准库函数检测字符串是否网址",inet.url.is(url) );
console.log("简单检测是否以http开始（忽略大小写）",string.startWith(url,"http",true) );

console.log("使用模式匹配检测字符串是否以https:或http:开始（忽略大小写）"
    ,string.match(url,"^<@@https@>|<@@http@>\:")
)

console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Text/matching.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Text/matching.md')

