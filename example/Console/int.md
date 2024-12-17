[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 控制台程�?- 拦截 Ctrl + C

```aardio aardio
//控制台程�?- 拦截 Ctrl + C
import console.int;

//拦截 Ctrl + C 等中断信�?var ctrlHandle = console.int();

ctrlHandle.run(
    function(){
        sleep(1000);
        console.log(time(),"�?Ctrl + C 退出！")
    }
)

/*
导入 console.int 以后�?线程退出时，如果控制台已打开会自动调�?console.pause()
*/

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Console/int.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Console/int.md')

