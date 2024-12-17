[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 控制台程序范�?- 自定义颜�?
```aardio aardio
//控制台程序范�?- 自定义颜�?
import console;
console.setTitle("自定义控制台颜色");

//修改整个控制台的颜色
for(name,clr in console.color){
    console.setColor(0xF-clr, clr);
    console.log("来来我是一个菠�?,name);
    sleep(100);
}

console.setColor();
console.pause();

//仅修改文本区的前景色与背景色
for(name,clr  in console.color){
    console.setTextAttribute(0xF-clr, clr);
    console.log("来来我是一个菠�?,name);
    sleep(100);

}
console.setTextAttribute();

//仅修改输出文本的颜色，并且恢复默认之前的颜色�?console.writeColorText("文本",console.color.yellow,console.color.darkGray);

console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Console/ColorConsole.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Console/ColorConsole.md')

