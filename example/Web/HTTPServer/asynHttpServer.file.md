[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: asynHttpServer - 扫码快传

```aardio aardio
//扫码传文�?import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="asynHttpServer - 扫码快传";right=807;bottom=465;bgcolor=16777215;border="none";max=false)
winform.add(
bk={cls="bk";left=-2;top=-5;right=810;bottom=29;bgcolor=12639424;z=9};
bkplus={cls="bkplus";text="asynHttpServer - 扫码传文�?;left=18;top=4;right=203;bottom=26;align="left";color=5921370;z=10};
btnOpen={cls="plus";text='\uF115';left=444;top=50;right=479;bottom=75;dr=1;dt=1;font=LOGFONT(h=-16;name='FontAwesome');notify=1;z=5};
btnOpenUpload={cls="plus";text="打开上传目录";left=568;top=429;right=709;bottom=458;dr=1;dt=1;font=LOGFONT(h=-15);iconStyle={align="left";font=LOGFONT(h=-15;name='FontAwesome');padding={left=8;top=2}};iconText='\uF115';notify=1;textPadding={left=20};z=11};
btnStart={cls="plus";text="重启服务";left=655;top=47;right=755;bottom=76;bgcolor=14935259;dr=1;dt=1;font=LOGFONT(h=-15);iconStyle={align="left";font=LOGFONT(h=-15;name='FontAwesome');padding={left=8;top=2}};iconText='\uF233';notify=1;textPadding={left=20};z=4};
editDocumentRoot={cls="plus";left=131;top=49;right=430;bottom=73;align="right";border={bottom=1;color=-8355712};dl=1;dr=1;dt=1;editable=1;font=LOGFONT(h=-16);z=7};
editPassword={cls="plus";left=441;top=84;right=632;bottom=108;align="left";border={bottom=1;color=-8355712};dl=1;dr=1;dt=1;editable=1;font=LOGFONT(h=-16);z=13};
editPort={cls="plus";left=550;top=49;right=628;bottom=73;align="left";border={bottom=1;color=-8355712};dl=1;dr=1;dt=1;editable=1;font=LOGFONT(h=-16);z=8};
plus={cls="plus";text="访问密码�?;left=332;top=90;right=433;bottom=114;align="right";dr=1;dt=1;font=LOGFONT(h=-15);transparent=1;z=12};
qr={cls="plus";left=499;top=132;right=760;bottom=418;db=1;dr=1;dt=1;repeat="scale";z=6};
static={cls="plus";text="端口�?;left=484;top=52;right=547;bottom=76;align="right";dr=1;dt=1;font=LOGFONT(h=-15);transparent=1;z=2};
static2={cls="plus";text="网站根目录：";left=15;top=52;right=129;bottom=76;align="right";dl=1;dt=1;font=LOGFONT(h=-15);transparent=1;z=3};
txtMessage={cls="richedit";left=42;top=132;right=469;bottom=418;autohscroll=false;db=1;dl=1;dr=1;dt=1;link=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

winform.btnStart.skin( {
    background={
        default=0x668FB2B0;
        hover=0xFF928BB3;
        disabled=0xFFCCCCCC;
    }
})

winform.btnOpen.skin( {
    background={
        default=0;
        hover=0xFF928BB3;
        disabled=0xFFCCCCCC;
    }
})

winform.btnOpenUpload.skin( {
    background={
        default=0;
        hover=0xFF928BB3;
        disabled=0xFFCCCCCC;
    }
})

import fsys.config;
config = fsys.config("/config/");
if( io.exist(config.winform.txtMessage) ){
    winform.txtMessage.text = config.winform.txtMessage;
}
else {
    winform.txtMessage.text = io.getSpecial(0x5/*_CSIDL_MYDOCUMENTS*/)
}

import web.socket.server;
var wsrv = web.socket.server();

var srvHttp = wsrv.httpServer;
/*
wsrv.httpServer 是实现单线程异步 HTTP 服务端的 wsock.tcp.asynHttpServer 对象�?浏览器组件发起异�?HTTP 请求支持 wsock.tcp.asynHttpServer。请不要�?inet.http �?阻塞请求同一线程创建�?asynHttpServer,这会导致 asynHttpServer 没有机会响应请求而导致死锁，
如果确有这样的需求，可创建线程发起请求，或改用基于多线程�?wsock.tcp.simpleHttpServer�?*/
srvHttp.documentRoot = winform.txtMessage.text;
srvHttp.userToken = string.random(18);
winform.editPassword.text = srvHttp.userToken;

import fsys.info;
var cacheSysIcons = {}
var getSysIconIndex = function(path){
    var sfi = fsys.info.get(path, 0x100/*_SHGFI_ICON*/ | 0x4000/*_SHGFI_SYSICONINDEX*/);
    if( !(sfi.returnValue ) ) {
        return;
    }

    if(!cacheSysIcons[sfi.iIcon]){
        var dataUrl;
        var bmp = ..gdip.bitmap(sfi.hIcon,1/*_IMAGE_ICON*/);
        if(bmp){
            cacheSysIcons[sfi.iIcon] = bmp.saveToBuffer(".png");
            bmp.dispose();
        }
    }
    if(sfi.hIcon)::DestroyIcon(sfi.hIcon);
    return sfi.iIcon;
}

var cacheClientIps = {}
srvHttp.run(
    function(response,request,session){

        var token = request.get["t"] : session["token"];
        if( #srvHttp.userToken && (token != srvHttp.userToken) ){
            winform.txtMessage.printf("客户端：%s 连接被拒�?,request.remoteAddr);
            response.errorStatus(401)
            return;
        }
        session["token"] = token;

        if(!cacheClientIps[request.remoteAddr]){
            winform.txtMessage.printf("客户端：%s 已连�?,request.remoteAddr);
            cacheClientIps[request.remoteAddr] = true;
        }

        response.headers["Access-Control-Allow-Origin"] = "*";
        response.headers["Access-Control-Allow-Headers"] = "*"

        if(request.path=="/main.aardio" && request.get["icon"]){
            var iconIdx = tonumber(request.get["icon"]);
            if(iconIdx!==null){
                if(cacheSysIcons[iconIdx]){
                    response.contentType = "image/png";
                    response.write(cacheSysIcons[iconIdx])
                    return;
                }
            }
            response.errorStatus(404);
            return;
        }

        if(request.path=="/upload/main.aardio"){
            if(request.method=="DELETE"){
                var path = request.postData();
                if(path && string.startWith(path,"/upload/")){
                    path = ..io.joinpath(srvHttp.documentRoot,path)

                    if(io.exist(path)){
                        io.remove(path);
                        winform.txtMessage.print("已删除：" + path);
                        response.close();
                        return;
                    }
                }

                response.errorStatus(404);
                return;
            }

            fileData = request.postFileData()
            if(fileData){
                io.createDir(..io.joinpath(srvHttp.documentRoot,"upload"))
                winform.txtMessage.print(..io.joinpath(srvHttp.documentRoot,"upload"))

                var fileName = ..io.joinpath(srvHttp.documentRoot,"upload",fileData.filepond.filename)
                var ok,err = fileData.filepond.save(fileName);
                if(!ok){ response.error(err); }

                winform.txtMessage.text = 'http服务端已启动: \n';
                winform.txtMessage.print( srvHttp.getUrl(,true) + "/?t=" + srvHttp.userToken  );

                winform.txtMessage.print( "" );
                winform.txtMessage.print( "上传成功�? + fileName );

                response.contentType = "text/plain";
                response.write("/upload/",fileData.filepond.filename)
                return response.close()
            }
        }

        if(!fsys.isDir(request.path) ) {
            if( ..io.exist(request.path)
                && (!_STUDIO_INVOKED || request.path!="/main.aardio") )
                return response.loadcode(request.path)
            else {
                request.path = fsys.getParentDir(request.path)
            }
        }

        response.write(`
<!doctype html>
<html>
<head>
<meta charset="utf-8">
<meta http-equiv="X-UA-Compatible" content="IE=edge" />
<title>asynHttpServer - 扫码快传</title>
<link href="https://lib.baomitu.com/filepond/4.28.2/filepond.min.css" rel="stylesheet">
<script src="https://lib.baomitu.com/filepond/4.28.2/filepond.min.js"></script>
<script>
(function (doc, win) {
    var docEl = doc.documentElement,
        recalc = function () {
            var clientWidth = docEl.clientWidth;
            if (!clientWidth) return;

            clientWidth=(clientWidth>640)?640:clientWidth;
            docEl.style.fontSize = ( (docEl.clientWidth>docEl.clientHeight) ? 12 : 20) * (clientWidth / 320) + 'px';
        };

    if (!doc.addEventListener) return;
    win.addEventListener('orientationchange' in window ? 'orientationchange' : 'resize', recalc, false);
    doc.addEventListener('DOMContentLoaded', recalc, false);
})(document, window);
</script>
<style>
html {
    padding:20px 0 0;
}
li{ list-style-type:none; }
</style>
</head>
<body>

<input type="file" class="filepond" name="filepond" multiple>
<script crossorigin="anonymous">
if(document.body.style.order === undefined){
    alert("浏览器版本过�?请使用Chrome或IE11以上版本浏览器打开此页�?")
}

var inputElement = document.querySelector('input[type="file"]');
FilePond.create(inputElement);
FilePond.setOptions({
    server: '/upload/?t=` + srvHttp.userToken + `',
    labelIdle: '拖放需要上传的文件到这里或�?<span class="filepond--label-action"> 浏览文件 </span>',
    labelFileProcessing: '上传�?..',
    labelFileProcessingComplete: '上传成功'
});

websocket = new WebSocket("`+wsrv.getUrl("ws",true)+`");
websocket.onmessage = function(evt) {
    if(evt.data=="reload"){
        window.location.pathname = "/";
        window.location.reload(true)
    }
};
</script>

<h2>当前目录：`
            ,request.path,`</h2><hr><ul>`)

        if(request.path=="/" && ..io.exist("/upload/")){
            response.write('<li><img src="/?icon='++getSysIconIndex("/upload/")+'"><a href="/upload?t=' + srvHttp.userToken + '">上传目录</a><br>\r\n');
        }

        var file,dir = fsys.list(request.path,,"*.*");
        for(i=1;#dir;1){
            if(dir[i]==="upload" && request.path=="/") continue;

            var iconIdex = getSysIconIndex(dir[dir[ i ]])
            response.write('<li><img src="/?icon='++(iconIdex)+'"><a href="'
                ,inet.url.append(request.path,dir[ i ])
                ,'?t=' + srvHttp.userToken + '">',dir[ i ],'</a><br>\r\n');
        }

        for(i=1;#file;1){
            var iconIdex = getSysIconIndex(file[file[ i ]])
            response.write('<li><img src="/?icon='++(iconIdex)+'"><a href="'
                    ,inet.url.append(request.path,file[ i ])
                    ,'?t=' + srvHttp.userToken + '">',file[ i ],'</a><br>\r\n');
        }

        response.write("</ul></body></html>")
    }
);

import qrencode.bitmap;
var serverInfo = function(){
    var ip,port = srvHttp.getLocalIp();
    winform.editPort.text = port;
    winform.editDocumentRoot.text = io.fullpath(srvHttp.documentRoot)

    var url = srvHttp.getUrl(,true);
    if(#srvHttp.userToken){
        url = url + "/?t=" + srvHttp.userToken;
    }

    winform.txtMessage.text = 'http服务端已启动: \n';
    winform.txtMessage.print(  url );

    var qrBmp = qrencode.bitmap( url );
    winform.qr.setBackground(qrBmp.copyBitmap(winform.qr.width));

    winform.txtMessage.print(
        "手机扫码可自动打开此网页，可以方便地上传下载文件�?拖动文件或目录到窗口上客户端网页会自动刷新�?
asynHttpServer 体积很小可嵌入任�?aardio 程序�?asynHttpServer 可以创建单线程异步模式的 HTTP 服务端，并可以同时创�?WebSocket 服务端（与HTTP服务端共享端口）。asynHttpServer 支持保持连接（Keep Alive），分块传输协议，支持断点续传，支持304缓存，支持文件表单上传，支持使用aardio编写的网站（ 接口可兼容IIS/FastCGI下）�?"
    );
}
serverInfo();

winform.btnStart.oncommand = function(id,event){
    winform.txtMessage.text = "";
    winform.btnStart.disabledText = {'\uF254';'\uF251';'\uF252';'\uF253';'\uF250'}
    win.delay(500);

    var port = tonumber(winform.editPort.text);
    srvHttp.documentRoot = fsys.isDir(winform.editDocumentRoot.text) ? winform.editDocumentRoot.text;
    srvHttp.userToken = winform.editPassword.text;
    srvHttp.start("0.0.0.0",port);
    serverInfo();

    winform.btnStart.disabledText = null;
}

import win.ui.menu;
winform.txtMessage.enablePopMenu();
winform.txtMessage.onHyperlink = function(message,href){
    if( message = 0x202/*_WM_LBUTTONUP*/ ) {
        import process;
        process.openUrl(href);
    }
}

winform.onDropFiles = function(files){
    var path = files[1]
    if(!fsys.isDir(path)){
        path = fsys.getParentDir(path)
    }
    winform.editDocumentRoot.text = path;
    srvHttp.documentRoot = path;
    config.winform.txtMessage = path;
    config.winform.save();

    wsrv.publish("reload");
}

import fsys.dlg.dir;
winform.btnOpen.oncommand = function(id,event){
    var dir = fsys.dlg.dir(winform.editDocumentRoot.text,winform)
    if(dir){
        winform.editDocumentRoot.text = dir;
        srvHttp.documentRoot = dir;

        config.winform.txtMessage = dir;
        config.winform.save();
        wsrv.publish("reload");
    }
}

import process;
winform.btnOpenUpload.oncommand = function(id,event){
    var path = io.joinpath(winform.editDocumentRoot.text,"upload")
    if(io.createDir(path)){
        process.explore(path)
    }
}

import win.ui.simpleWindow2;
win.ui.simpleWindow2(winform);
winform.show();

import fsys;
fsys.attrib("/config/",,2/*_FILE_ATTRIBUTE_HIDDEN*/)

win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/HTTPServer/asynHttpServer.file.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/HTTPServer/asynHttpServer.file.md')

