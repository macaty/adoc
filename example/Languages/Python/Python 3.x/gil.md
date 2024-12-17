[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?aardio 中使�?Python 多线�?GIL

```aardio aardio
//�?aardio 中使�?Python 多线�?GIL
import win.ui;
/*DSG{{*/
var winform = win.form(text="Python 3 - 多线�?GIL";right=1163;bottom=753)
winform.add(
button={cls="button";text="点这里试�?;left=876;top=663;right=1102;bottom=723;z=2};
edit={cls="edit";left=11;top=16;right=1140;bottom=625;edge=1;multiline=1;z=1}
)
/*}}*/

/*
Python 多线程有很多限制，用起来也复杂，一般不建议用�?这是 Python 的限制与 aardio 无关！不信可以换个编程语言试试�?要解�?Python 这个限制很容易，Python 开源的，请放开手干！！�?
要点1、一定要在主线程导入 Python �?主线程会负责创建 Python 虚拟机，主线程退出不能再在任何线程调�?Python.
*/
import py3;//不同线程导入不同版本�?Python 会崩�?
/*
要点2、一定要在主线程释放GIL，之后任何python调用都在在py.lock里执�?注意，只有你确实要在多个线程并发调用python时，才需要使用GIL�?*/
py3.releaseThread();

pyThread = function(winform){
    import py3;

    /*
    要点3、启�?GIL 以后，任�?Python 调用都必须在 py.lock 里执�?    Python 并不支持真正的多线程,所有调用都要加锁互斥运行�?    */
    py3.lock(
        function(){
            var hashlib = py3.import("hashlib");
            var md5 = hashlib.md5()
            md5.update( raw.buffer("注意这个函数的参数不是字符串而是字节数组（相当于aardio中的buffer�?) );
            winform.edit.print(thread.getId(), tostring(md5.hexdigest()) );
        }
    )
}

winform.button.oncommand = function(id,event){

    for(i=1;10;1){
        thread.invoke( pyThread,winform )
    }
}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/gil.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/gil.md')

