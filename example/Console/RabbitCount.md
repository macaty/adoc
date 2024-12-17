[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 控制台程序范�?- 兔子总数为多�?
```aardio aardio
//控制台程序范�?- 兔子总数为多�?import console;

console.log("问题：兔子出生两月以后就有繁殖能力，一对兔子每月能生出一对小兔子�?现有一对有繁殖能力的兔子，如果所有兔子都不死，请�?4个月后可繁殖多少对兔子？
");

var f1,f2=1,1;
for( i=1;14) {
    f1,f2=f1+f2,f1;//前两个月加起�?f1=f1+f2)赋值给第三个月,f2再与上个月交换�?f2=f1)
    console.printf('共有兔子 %12.0f�?经过%d�?',f1,i);
};

console.log("
兔子的规律为斐波那契数列：f[0]=0 f[1]=1 如果i>=2 f[i] = f[i-1]+f[i-2]
----------------------------------------------------------
")

var f1,f2=1,1;
for( i=1;16 )  {
    var str = string.format('%12d',f1);
    io.stdout.write(str);

    //如果i能整�?(4的倍数)即输入一个换�?io.print('')函数可自动添加换�?    if( i % 4 ==0 ) { io.print( ""  ) };
    f1,f2 = f2,f1+f2;
};

console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Console/RabbitCount.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Console/RabbitCount.md')

