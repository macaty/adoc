[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 计划任务

```aardio aardio
//计划任务
import win.ui;
/*DSG{{*/
var winform = win.form(text="计划任务";right=599;bottom=399)
winform.add(
edit={cls="edit";left=16;top=24;right=592;bottom=384;edge=1;hscroll=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

//创建计划任务
import win.taskScheduler;
var taskScheduler = win.taskScheduler( winform );

var task  = taskScheduler.create("间隔一秒执�?,function(){
    winform.edit.print( "间隔一秒执�?,time() );
} )

//设定计划任务执行时间方案
task.interval = {
   second = 1;
}

var task2 = taskScheduler.create("每次�?23:28 分执�?,function(){
    winform.edit.print( "每次�?20:28 分执�?,time() );

    //可创建线程执行耗时任务
    thread.invoke(
        function(winform){

        },winform
    )
} )

//设定计划任务执行时间方案
task2.time = {
    minute = 28;
    hour = 20 ;
}

//启动计划任务
taskScheduler.start();

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/aardio/DateTime/win.taskScheduler.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/aardio/DateTime/win.taskScheduler.md')

