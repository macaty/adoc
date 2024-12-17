[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: COM 接口 - 查看对象

```aardio aardio
//COM 接口 - 查看对象
import win.ui;
/*DSG{{*/
var winform = win.form(text="获取COM对象成员列表";right=759;bottom=469)
winform.add(
edit={cls="richedit";left=15;top=10;right=744;bottom=443;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

winform.edit.limit = 0xFFFFF;

//创建 COM 对象,注意服务器系统没这个控件
var wmPlayer = com.CreateObject("WMPlayer.OCX");

//输出 COM 对象支持的属性和方法
//winform.edit.print( com.DumpTypeInfo(wmPlayer) )
//也可以通过 console.dump(wmPlayer) 自动调用 com.DumpTypeInfo(wmPlayer)

//输出更详细的 COM 对象类型库文�?import com.tlbDoc;
var tlbDoc = com.tlbDoc( wmPlayer );
winform.edit.print(tlbDoc);

//这里定义一个事件监听器，目的是拦截所有事件名�?com.Connect(wmPlayer,  {
    @{ _get = function(eventName){
        winform.edit.print("此对象支持事�?",eventName)
    } }
});

wmPlayer.url = "http://download.aardio.com/v10.files/demo/mp3/lrc.mp3"

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/GettingStarted/DumpTypeInfo.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/GettingStarted/DumpTypeInfo.md')

