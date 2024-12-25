[aardio 文档](../index.htm "aardio 编程语言文档首页")

# aardio 范例: 快速入�?- 第一�?aardio 程序

```aardio aardio
//快速入�?import win.ui;
/*DSG{{*/
var winform = win.form(text="快速入�?- 第一�?aardio 程序";right=757;bottom=467)
winform.add(
edit={cls="richedit";left=6;top=6;right=754;bottom=464;db=1;dl=1;dr=1;dt=1;edge=1;link=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

//导入 web.json 库，文本框就能以 JSON 格式输出对象
import web.json;

//文本框内输出任意对象
winform.edit.print({
    number = 123; //数�?    string = "原始字符串，不处理转义符";
    escapedString  = '单引号包含转义字符串，处理转义符。例如回车换行\r\n';
    blockComment = /*
注释可以赋值为字符�?

语法速览: https://www.aardio.com/zh-cn/doc/guide/language/syntax-quick-ref.html
特殊符号大全: https://www.aardio.com/zh-cn/doc/guide/language/special-characters.html
快捷键与小技�? https://bbs.aardio.com/forum.php?mod=viewthread&tid=13220&from=portal
模式匹配入门: https://www.aardio.com/zh-cn/doc/guide/language/pattern-matching.html
魔法 web.rest: https://www.aardio.com/zh-cn/doc/library-guide/std/web/rest/client.html
创建窗口控件: https://www.aardio.com/zh-cn/doc/library-guide/std/win/ui/create-winform.html
制作精美界面: https://bbs.aardio.com/forum.php?mod=viewthread&tid=11486&from=portal
*/;
    object = { //对象（表�?        name = "object";
        value = {
            object = {
                name = "object.object"
            }
        }
    };
    array = {1,2,3,4,5,6,7};//数组，数据类型也是表（table�?    buffer = raw.buffer("二进制字节数�?);
    pointer = topointer(1);//原生指针
    time = time.now();//日期时间
    boolean = true || false;//布尔�?});

//继续打印，不会覆盖之前的内容�?winform.edit.print("�?aardio 快速入门教�?�?https://mp.weixin.qq.com/mp/appmsgalbum?__biz=MzA3Njc1MDU0OQ==&action=getalbum&album_id=2209804829378543621
");

//定义一个回调函数，在richedit 控件中点击链接时自动触发此函数�?winform.edit.onHyperlink = function(message,href){

    if( message = 0x202/*_WM_LBUTTONUP*/ ) {
        raw.execute(href);
    }
}

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/QuickStart.md)

