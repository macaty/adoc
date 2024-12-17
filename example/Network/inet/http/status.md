[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: HTTP 状态码、错误代码检�?- aardio

```aardio aardio
//错误码检�?import win.ui;
/*DSG{{*/
var winform = win.form(text="HTTP 状态码、错误代码检�?- aardio";right=485;bottom=347;)
winform.add(
btnCheck={cls="button";text="检�?;left=393;top=30;right=455;bottom=56;z=2};
editResult={cls="richedit";left=10;top=62;right=473;bottom=341;edge=1;font=LOGFONT(name='Microsoft Sans Serif');hscroll=1;link=1;multiline=1;vscroll=1;wrap=1;z=3};
editUrl={cls="edit";text="http://eu.httpbin.org/status/402";left=43;top=32;right=387;bottom=54;edge=1;multiline=1;z=1};
static={cls="static";text="请输入网址、或直接输入 HTTP 状态码、错误代�?";left=12;top=9;right=299;bottom=25;transparent=1;z=4}
)
/*}}*/

//开启自动完�?::Shlwapi := ..raw.loadDll("Shlwapi.dll")
::Shlwapi.SHAutoComplete( winform.editUrl.hwnd,0/*_SHACF_DEFAULT*/);

import inet.url;
import inet.errorMessage;
winform.btnCheck.oncommand = function(id,event){

    var url = winform.editUrl.text;
    if(! ..inet.url.is(url) ){
        if( tonumber(url) ){
            import inet.httpStatusCode;
            winform.editResult.text = inet.httpStatusCode[tonumber(url) ] || inet.errorMessage[tonumber(url)]  || "未知错误代码"
            return;
        }
        winform.msgboxErr("请输入正确的网址");
        winform.editUrl.setFocus(0,-1);
        return;
    }

    //禁用按钮,避免重复点击
    winform.btnCheck.disabled = true;
    winform.editResult.text = "请稍�?正在连接......."

    winform.editResult.text = thread.invokeAndWait(
        function(url){
            import inet.http;
            import inet.httpStatusCode;
            import inet.errorMessage;

            //创建http对象
            var http = inet.http();
            if( !http.beginRequest( url,"HEAD",,,0x200000/*_INTERNET_FLAG_NO_AUTO_REDIRECT*/ ) ) {
                http.close();
                return "无效的请�?;
            }

            //发送请�?            var ret,errMsg,errCode = http.send();
            if(http.statusCode){
                var msg = string.concat( "返回状态码�?, http.statusCode + '\r\n'
                    , inet.httpStatusCode[http.statusCode] ,'\r\n',http.readHeader() ,);

                http.close();
                return msg;
            }
            else {
                http.close();

                if( type(errCode) == type.number ){
                    var msg = "请求失败,错误代码�? + errCode + '\r\n'
                        + ( inet.errorMessage[errCode] : "")

                    if( errCode == 12003 ) msg = ..string.concat(errCode,'\r\n',inet.lastResponse() );

                    return msg;
                }
                return"请求失败";

            }
        },url
    )

    winform.btnCheck.disabled = false;
}

import ide;
win.setOwner(winform.hwnd,ide.getMainHwnd());

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/inet/http/status.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/inet/http/status.md')

