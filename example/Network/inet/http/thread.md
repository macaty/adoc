[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 获取 HTML

```aardio aardio
//多线�?import win.ui;
/*DSG{{*/
var winform = win.form(text="获取 HTML";right=759;bottom=469)
winform.add(
btnGetUrl={cls="button";text="获取 HTML";left=481;top=376;right=713;bottom=432;color=14120960;db=1;dr=1;font=LOGFONT(h=-14);note="创建工作线程请求目标网址";z=2};
editHtml={cls="edit";left=29;top=24;right=735;bottom=361;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=1};
editUrl={cls="edit";text="http://www.aardio.com";left=33;top=385;right=453;bottom=413;db=1;dl=1;dr=1;edge=1;multiline=1;z=3}
)
/*}}*/

winform.btnGetUrl.oncommand = function(id,event){
    winform.btnGetUrl.disabled = true;

    //创建工作线程
    thread.invoke(
        function(winform){
            import inet.http;

            //创建 HTTP 对象
            var http = inet.http();

            /*
            http 发送请求是耗时操作 —�?会阻塞当前线程�?            在界面线程可能会导致卡顿 —�?当然速度很快是感觉不出来的�?            创建工作线程就可以避免这一问题�?            */
            var data  = http.get(winform.editUrl.text);

            //显示抓取结果
            winform.editHtml.text = data;

            //启用按钮
            winform.btnGetUrl.disabled = false;
        },winform /*将窗口对象作为参数传入线程函�?/
    )

    /*
    //inet.http.get() 会自动创建线程并发�?GET 请求然后返回响应数据�?    import inet.http;
    winform.editHtml.text = inet.http.get(winform.editUrl.text);
    winform.btnGetUrl.disabled = false;
    */
}

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/inet/http/thread.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/inet/http/thread.md')

